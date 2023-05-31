# RingCentral Video SDK UIKit - Android  

## 1. RingCentral Video SDK UIKit-Android Introduction

- RingCentral Video SDK UIKit - Android is a UI component libraries based on RingCentral  Video Client SDK (Android).
- This UI component library implements some of the main business logic for RingCentral Video Meeting, so it is not a pure UI component library.  
- Users can use these functions simply by integrating the component library.

## 2. RingCentral Video SDK UIKit Components

<div align="left"><img src=README.assets/image-20230406104322761.png width=300></div>

### 2.1 Meeting Top Bar

#### 2.1.1 Audio Route Action

Audio route supports three modes：Speake mode<img src=README.assets/speaker.png width=40>, iPhone mode<img src=README.assets/iphone.png width=40>, Bluetooth mode<img src=README.assets/blooth.png width=40>
If you're not connected to a bluetooth device, you can tap the audio route button to switch between the speaker and the iPhone.  
If you're connected to a bluetooth device, it automatically switches to bluetooth mode, and then you can click the audio route button to switch between speaker and bluetooth.  
If the bluetooth is disconnected, switch back to the previous mode.

#### 2.1.2 Meeting Chat Action

Click the `Chat` button<img src=README.assets/chat.png width=40> to enter the meeting chat page. The page contains two tab pages "With everyone" and "Privately", the `WITH EVERYONE` page is taken by default.  

<div align="left"><img src=README.assets/image-20230406110501339.png width=300></div>

You can send a messages from this page, and all participants in the meeting can see your messages.
 Click the `PRIVATELY` to go to the privately page.

<div align="left"><img src=README.assets/image-20230406111423826.png width=300></div>

You can chat with someone in the meeting, and other members of the meeting cannot see your chat messages.  
On the Privately page, click the + button in the upper middle and select who you want to chat with in the participants list that pops up

<div align="left"><img src=README.assets/image-20230406111423826.png width=300 style="margin-right:10px;"><img src=README.assets/image-20230406112046772.png width=300 style="margin-right:10px;" ><img src=README.assets/image-20230406164242109.png width=300></div>

#### 2.1.3 Meeting Info Action

Click the `Meeting Info` button<img src=README.assets/meetinginfo.png width=30> to display the details of the meeting:

<div align="left"><img src=README.assets/image-20230406113319407.png width=300></div>

#### 2.1.4 Leave Action

In the meeting, the `Leave` button<img src=README.assets/leave.png width=30> will be displayed, and clicking it will leave the current meeting.

### 2.2 Meeting Bottom Bar

#### 2.2.1 Meeting Audio Action

You can control the local audio mute and unmute by the Audio button.  

### 2.2 Meeting Bottom Bar

#### 2.2.1 Meeting Audio Action

You can control the local audio mute and unmute by the Audio button.  

<div align="left"><img src=README.assets/image-20230406122236963.png width=300 style="margin-right:10px;"><img src=README.assets/image-20230406122247903.png width=300 style="margin-right:10px;"></div>

#### 2.2.2 Meeting Video Action

You can control the local video mute and unmute by the video button

<div align="left"><img src=README.assets/image-20230406171348734.png width=300 style="margin-right:10px;"><img src=README.assets/image-20230406122548173.png width=300 style="margin-right:10px;"></div>

#### 2.2.3 Participants List Action

Click the `Participants` button <img src=README.assets/participants.png width=40> to display the participants list page, showing the current situation of participants in the meeting.

<div align="left"><img src=README.assets/image-20230406122949358.png width=300></div>

#### 2.2.4 Screen Sharing Action

You can click the `Share` button to control screen sharing.  Click the button and a popup appears. Click `Start Now`.

<div align="left"><img src=README.assets/image-20230406164407133.png width=300 style="margin-right:10px;"><img src=README.assets/image-20230406161742467.png width=300 style="margin-right:10px;"><img src=README.assets/image-20230406161807310.png width=300"></div>



When receiving a shared screen from another member.

<div align="left"><img src=README.assets/image-20230406162112359.png width=300></div>

#### 2.2.5 Meeting Recording Action

When you are the host or moderator, you can control the start/pause/resume recording.

<div align="left"><img src=README.assets/image-20230406161249171.png width=300 style="margin-right:10px;"><img src=README.assets/image-20230406161425153.png width=300 style="margin-right:10px;"><img src=README.assets/image-20230406161523562.png width=300></div>

### 2.2.5 More Action

This action is aim to add the button besides what was mentioned above, or the custom button need to be add to meeting bottom bar.
as the follow picture shows, the invite others,closed caption,virtual background buttons are add to more meeting bottom bar.
<div align="left"><img src=README.assets/image_20230428_101855.png width=300 style="margin-right:10px;"><img src=README.assets/image_20230428_102000.png width=300 style="margin-right:10px;"></div>

#### 2.2.6 Invite Others Action

You can click `More` button first, and then click `Invite others` button. 

<div align="left"><img src=README.assets/image_20230428_101855.png width=300 style="margin-right:10px;"><img src=README.assets/image_20230428_103700.png width=300 style="margin-right:10px;"></div>

There will show a popup, you can choose invite other by copy meeting link, or invite by email.

<div align="left"><img src=README.assets/image_20230428_102008.png width=300 style="margin-right:10px;"></div>

if you choose invite by copy meeting link, the meeting link will copy to system clipboard.

<div align="left"><img src=README.assets/image_20230428_102051.png width=300 style="margin-right:10px;"></div>

Corresponding to above, if you choose invite by email, uikit will generate the email content, you can choose a email app to send it.

<div align="left"><img src=README.assets/image_20230428_102102.png width=300 style="margin-right:10px;"><img src=README.assets/invite_by_email.png width=300 style="margin-right:10px;"></div>

#### 2.2.7Live Transcription

Live Transcription, short name is LT, is real-time speech transcription. If your account supports LT, its button will be displayed in more menu when LT service is ready, as shown below:

<div align="left"><img src=README.assets/image-20230530134102053.png width=300>----><img src=README.assets/image-20230530134229148.png width=300></div>

Click the LT button to enter the LT page:

<div align="left"><img src=README.assets/image-20230530153622464.png width=300></div>

When someone speaks during the meeting, the LT transcript is displayed on the LT page:

<div align="left"><img src=README.assets/image-20230530160449846.png width=300></div>

The LT page supports content search. Enter the content to be searched in the search box:

<div align="left"><img src=README.assets/image-20230530160611273.png width=300></div>

To the right of the search box is the LT control button, which can control the start and pause of the LT, visible only to the host or moderator:

<div align="left"><img src=README.assets/image-20230530160716895.png width=300></div>

If LT is enabled, the LT button in the more menu changes to view transcription:

<div align="left"><img src=README.assets/image-20230530134318809.png width=300></div>

### 2.3 Layout

There are currently two layouts, gallery and active speaker. The default layout is active speaker. When there are more than one person in a meeting, the layout selection button is displayed to select the appropriate layout.

<div align="left"><img src=README.assets/image-20230530131551746.png width=300></div>



#### 2.3.1 Gallery 

This is the layout of the  RingCentral Video SDK UIKit-Android main page. Sliding pages are adopted. Basic information of up to three participants is displayed on each page.  
Each participant has a corresponding cell in the gallery, used to display the participant of the video/avatars and other information.

<div align="left"><img src=README.assets/image-20230406133026908.png width=300></div>



#### 2.3.2 Active Speaker

Display the active speaker in the middle. If no one is speaking, the first member who is not your own member is used by default. If the speaker changes, the screen switches. The video screen of the active speaker is displayed in the center area, and the network, audio, and name of the active speaker are displayed in the lower left corner.

<div align="left"><img src=README.assets/image-20230530132444486.png width=300></div>

If local video is enabled, the image is displayed in the lower left corner of the lay out layout. You can drag to move the local video.

The camera switch button[![img](README.assets/cameraButton.png)in the upper right corner of the local video screen allows you to switch between the front and rear cameras.

<div align="left"><img src=README.assets/image-20230530132959944.png width=300 style="margin-right:10px;"><img src=README.assets/image-20230530133021735.png width=300 style="margin-right:10px;"><img src=README.assets/image-20230530133114909.png width=300"></div>



## 3. How to integrate RingCentral Video SDK UIKit

The RingCentral Video SDK UIKit-Android component library implements the UI and business after successfully joining a meeting, so the application layer needs to finish the below tasks before the meeting

### 3.1 Preparatory

- **Building A Project With Java/Kotlin**

1. If you are using a Gradle version lower than 6.8.0, add the following lines to your **build.gradle** file. Instead, you can ignore this step.

   ```groovy
   allprojects {
       repositories {
           google()
           mavenCentral()
       }
   }
   ```

2. Add it in your root **build.gradle** at the end of repositories.

   ```groovy
   allprojects {
       repositories {
           ...
           maven { url 'https://s01.oss.sonatype.org/content/repositories/releases' }
       }
   }
   ```

3. Add the following lines under **dependencies** of your app **build.gradle** file.

   ```groovy
   implementation 'com.pubnub:pubnub-gson:4.29.2'
   implementation 'com.squareup.okhttp3:okhttp:4.9.1'
   implementation 'com.ringcentral.video:ringcentral-video-sdk:version'
   implementation 'com.ringcentral.video:ringcentral-video-sdk-uikit:version'
   implementation "io.github.scwang90:refresh-layout-kernel:2.0.6"
   implementation "io.github.scwang90:refresh-header-classics:2.0.6"
   ```

3. Open the **gradle.properties** file in the root directory of your project.

   If the line `android.enableJetifier=true` and `android.useAndroidX=true` doesn't exist in the file, you can add it directly at the end. If the line already exists but its value is `false`, you can change it to `true`.
   
   ```groovy
   android.useAndroidX=true
   android.enableJetifier=true
   ```

- **Create a RingCentral Client Video SDK instance**

  1. Use your client ID and client secret to initial the RCV client SDK engine as code below, the client ID and client secret are required.

  ```kotlin
  RcvEngine.create(this.getApplicationContext(), <#client ID#>, <#client secret#>)
  ```

  2. If you intend to host a meeting or access your extension information, such as the meeting list or the recording list, etc, follow the steps in our [RingCentral Video client SDK Dev Guide](https://ringcentral-ringcentral-video-api-docs.readthedocs-hosted.com/en/latest/client-sdk/authentication/) to procure the RingCentral authorization tokens and invoke the API method as code below.
  ```kotlin
  RcvEngine.instance().setAuthToken(<#authorization token string#>, true);
  ```

- **Create and bind a Service in Android, you can follow these steps**

  1. Register the MeetingService and ScreenCaptureService in the AndroidManifest.xml file. To do this, add the following line in the <application> tag:
  ```xml
  <service android:name="com.ringcentral.video.uikit.service.MeetingService"
              android:enabled="true"
              android:exported="false"
              android:foregroundServiceType="camera|microphone" />
  
  <service
              android:name="com.ringcentral.video.uikit.service.ScreenCaptureService"
              android:enabled="true"
              android:foregroundServiceType="mediaProjection"/>
  ```
  2. In the application's Activity or Fragment, create a ServiceConnection object to communicate with the Service. The ServiceConnection object will receive notifications when the Service is successfully bound or disconnected.

  3. Bind the Service using the bindService() method in the Activityor Fragment and pass the ServiceConnection object. For example:
  ```kotlin
  Intent(this.context, MeetingService::class.java).also { intent ->
      requireContext().bindService(intent, connection, Context.BIND_AUTO_CREATE)
  }
  ```
  
  4. Implement the onServiceConnected() and onServiceDisconnected() methods in the ServiceConnection object to receive notifications when the Service is successfully bound or disconnected. For example:
  ```kotlin
  private lateinit var meetingService: MeetingService
      private val connection = object : ServiceConnection {
          override fun onServiceConnected(name: ComponentName?, service: IBinder?) {
              val binder = service as MeetingService.MeetingServiceBinder
              meetingService = binder.getService()
          }
        
          override fun onServiceDisconnected(name: ComponentName?) {
          }
  }
  ```
  
- **Start or Join a meeting**

### 3.2 How to use RingCentral Video SDK UIKit

The RingCentral Video SDK UIKit component externally provides the navigation file.   
The APP layer only needs to display the RCVMeetingView after the success of the start or join a metting. The example code is as follows:  

```kotlin
private val engineEventHandler = EventHandlerImpl()

override fun onCreate(savedInstanceState: Bundle?) {
  super.onCreate(savedInstanceState)
  RcvEngine.instance().registerEventHandler(engineEventHandler)
}

inner class EventHandlerImpl : EngineEventHandler() {
  override fun onMeetingJoin(meetingId: String?, errorCode: Long) {
   var joinResult = RcvEngine.getErrorType(errorCode)
   when (joinResult) {
     	ErrorCodeType.ERR_OK -> {
       	val bundle = bundleOf(RCVMeetingView.ARG_MEETING_ID to meetingId)
       	val navController = Navigation.findNavController(this@MainActivity, R.id.nav_host_fragment)
       	navController.setGraph(com.ringcentral.video.uikit.R.navigation.meeting_graph, bundle)
     	}
     	else -> {}
   }
 }
 ...
}
```

