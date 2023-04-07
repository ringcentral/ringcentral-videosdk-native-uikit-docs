# RCVUIKit how to start screen share

## How it works
Since Apple doesn't support screen capture in the main app process, you need to create a separate Extension for the screen sharing stream, use the native iOS ReplayKit framework to record the screen in the Extension, and then send the screen sharing stream to the main process for screen sharing.

## How to do it

#### 1. select File -> Target -> Broadcast Upload Extension. make a new Extension
<div align="left"><img src=img/image-20230406112527830.png width=300></div>

#### 2. Select You Extension 

<div align="left"><img src=img/image-20230406112655768.png width=300></div>

#### 3. Add the framework(RcvRelayKitExtension.xcframework) to you You Extension  maked in step 1

<div align="left"><img src=img/image-20230406112714169.png width=300></div>

#### 4. Because according apple we should set the same group id between App And Extension

<div align="left"><img src=img/image-20230406112751991.png width=300></div>

#### 5. Now we add the same group id both Extension amd App. Such as "group.com.xxx.xxx.xxx"

<div align="left"><img src=img/image-20230406112853303.png width=300></div>
#### 6. now write Extension as follow.notice you should replace you own group 

`return "group.com.ringcentral.rcv.sample"` this line should replace your own group id



```Swift

//
//  SampleHandler.swift
//  RcvBroadcastExtension
//
//  Created by Conch Feng on 8/6/2022.
//

import ReplayKit
import RcvReplayKitExtension

class SampleHandler: RPBroadcastSampleHandler {
    private var appGroupName: String {
        //replace with Your App Group Identifier.
        return "group.com.ringcentral.rcv.sample"
    }

    func createRcvService() -> RcvScreenShareService {
        let result = RcvScreenShareService()
        result.appGroup = appGroupName
        result.delegate = self
        return result
    }

    var rcvService: RcvScreenShareService?
    
    override init() {
        super.init()
    }

    deinit {
        rcvService?.delegate = nil
        rcvService = nil
    }
    
    override func broadcastStarted(withSetupInfo setupInfo: [String : NSObject]?) {
        let rcvSvc = createRcvService()
        if rcvSvc.broadcastStarted(withSetupInfo: setupInfo) {
            rcvService = rcvSvc
        }
        print("broadcastStarted:\(setupInfo ?? [:])")
    }
    
    override func broadcastPaused() {
        if let rcvService = rcvService {
            rcvService.broadcastPaused()
        }
        print("broadcastPaused")
    }
    
    override func broadcastResumed() {
        if let rcvService = rcvService {
            rcvService.broadcastResumed()
        }
        print("broadcastResumed")
    }
    
    override func broadcastFinished() {
        if let rcvService = rcvService {
            rcvService.broadcastFinished()
        }
        print("broadcastFinished")
    }
    
    override func processSampleBuffer(_ sampleBuffer: CMSampleBuffer, with sampleBufferType: RPSampleBufferType) {
        if let rcvService = rcvService {
            rcvService.processSampleBuffer(sampleBuffer, with: sampleBufferType)
        }
    }
}


extension SampleHandler: RcvScreenShareServiceDelegate {
    private func rcvScreenShareServiceErrorToString(errorCode: Int) -> String {
        switch errorCode {
        case RCVRPRecordingErrorCommunication, RCVRPRecordingErrorSharingHasBeenFailed:
            return "The screen sharing has been stopped due to internal error."
        case RCVRPRecordingErrorMeetingOrSharingEnded:
            return "The screen sharing or the meeting has been ended."
        case RCVRPRecordingErrorSharingHasBeenCancelled, RCVRPRecordingErrorLostConnectionToHostApp:
            return "Screen sharing has ended."
        case RCVRPRecordingErrorSharingHasBeenInterrupted:
            return "Another participant has started screen sharing."
        case RCVRPRecordingErrorMeetingHasBeenEnded:
            return "This meeting has ended."
        default:
            return ""
        }
    }

    func rcvScreenShareServiceFinishBroadcastWithError(_ error: Error) {
        let nsError = error as NSError
        let errorString = rcvScreenShareServiceErrorToString(errorCode: nsError.code)
        var userInfo = nsError.userInfo
        print("finishRCVBroadcastWithError:\(nsError.code)")
        userInfo[NSLocalizedDescriptionKey] = errorString
        userInfo[NSLocalizedFailureReasonErrorKey] = errorString
        finishBroadcastWithError(NSError(domain: nsError.domain, code: nsError.code, userInfo: userInfo))
    }
}

```

#### 7. you should also in you main app use `RcvEngine.instance().setAppGroupName("group.com.ringcentral.rcv.sample")`	 notice you should replace group id with your own
<div align="left"><img src=img/image-20230406113407210.png width=300></div>


###  now it should use screen sharing function