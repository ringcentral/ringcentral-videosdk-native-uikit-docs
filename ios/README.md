# RCVUIKit - iOS  

## 1.RCVUIKit-iOS Introduction
RCVUIkit-iOS is a UI component libraries based on RingCentral Client Video SDK(iOS).   
This UI component library implements some of the main business logic for RingCentral Video Meeting, so it is not a pure UI component library.  
Users can use these functions simply by integrating the component library.

## 2.RCVUIKit Components

<div align="left"><img src=img/componet.png width=300></div>

### 2.1 Meeting Top Bar
#### 2.1.1 Audio Route Action
Audio route supports three modes：Speake mode<img src=img/speaker.png width=40>, iPhone mode<img src=img/iphone.png width=40>, Bluetooth mode<img src=img/blooth.png width=40>  
If you're not connected to a bluetooth device, you can tap the audio route button to switch between the speaker and the iPhone.  
If you're connected to a bluetooth device, it automatically switches to bluetooth mode, and then you can click the audio route button to switch between speaker and bluetooth.  
If the bluetooth is disconnected, switch back to the previous mode.

#### 2.1.2 Meeting Chat Action
Click the Chat button<img src=img/chat.png width=40> to enter the meeting chat page. The page contains two tab pages "With everyone" and "Privately", the "With everyone" page is taken by default.  

<div align="left"><img src=img/everyone.png width=300></div>

You can send a messages from this page, and all participants in the meeting can see your messages.  
Click the Privately to go to the privately page.  

<div align="left"><img src=img/privately.png width=300></div>

You can chat with someone in the meeting, and other members of the meeting cannot see your chat messages.  
There are two ways to choose a chat partner on privately:

- On the Privately page, click the + button in the upper middle and select who you want to chat with in the participants list that pops up  

  <div align="left"><img src=img/chatParticipantsList.png width=300></div>

- Select an participant to chat with from the participant list described in Section 2.2.3    

  <div align="left"><img src=img/participantList.png width=300></div>

Select the corresponding participant to enter its chat page:

<div align="left"><img src=img/privateChat.png width=300></div>

#### 2.1.3 Meeting Info Action
Click the "meeting info" button<img src=img/meetinginfo.png width=40> to display the details of the meeting:  

<div align="left"><img src=img/meetingDetails.png width=300></div>

#### 2.1.4 Leave/End Meeting Action
If you're a host or a morderator, the End button<img src=img/end.png width=40>displays, and when clicked, the action option pops up, which you can select as needed   

<div align="left"><img src=img/endOptions.png width=300></div>

If you are a regular participant, the leave button<img src=img/leave.png width=40> will be displayed, and clicking it will leave the current meeting.

### 2.2 Meeting Bottom Bar
#### 2.2.1 Meeting Audio Action
You can control the local audio mute and unmute by the Audio button.  

<div align="left"><img src=img/audioMute.png width=300><img src=img/audioUnmute.png width=300></div>

#### 2.2.2 Meeting Video Action
You can control the local video mute and unmute by the video button 

<div align="left"><img src=img/startVideo.png width=300><img src=img/stopVideo.png width=300></div> 

#### 2.2.3 Participants List Action
Click the Participants button<img src=img/participants.png width=40> to display the participants list page, showing the current situation of participants in the meeting.  
If you are host or moderator, you can do remote audio/video mute/unmute here.

<div align="left"><img src=img/participantList.png width=300><img src=img/participantMore.png width=300></div> 



#### 2.2.4 More Action

Some other extension functions are placed in the More menu, click the More button, you can pop up the menu list, select the required functions, currently there are four functions: recording, invite, closed captions and live transcription, later can support customization.

<div align="left"><img src=img/morePage.png width=300><img src=img/moreMenu.png width=300></div>

##### 2.2.4.1 Meeting Recording Action

The recording button<img src=img/startRecord.png width=40> will be displayed in the Meeting Bottom Bar if your account has recording rights, otherwise it will not be displayed. With this button you can control start/pause/resume  recording. 

<div align="left"><img src=img/record.png width=300><img src=img/pause.png width=300><img src=img/resume.png width=300></div>

##### 2.2.4.2 Invite Others Action

Currently, two invite methods are supported: copy meeting link and email. If you want to invite by email, you need to set an email account on your device. Otherwise, you can't invite others by email.

<div align="left"><img src=img/invitePage.png width=300><img src=img/inviteOptions.png width=300></div>

##### 2.2.4.3 Closed Captions

Closed captions is hidden captions.  When a meeting member is speaking, the voice can be converted into subtitles and displayed on the screen. The current support for English is good. Click the CC button<img src=img/ccbutton.png width=40> to enable the CC function. Click<img src=img/discc.png width=40>  again to disable the CC function.

CC subtitles will be displayed for 5 seconds. If no one speaks for more than 5 seconds, the subtitles will disappear.

<div align="left"><img src=img/enableCC.png width=300><img src=img/CC.png width=300><img src=img/DisableCC.png width=300></div>



##### 2.2.4.4 Live Transcription

Live Transcription, short name is LT, is real-time speech transcription. If your account supports LT, its button will be displayed in more menu when LT service is ready, as shown below:

<div align="left"><img src=img/MoreNoLt.jpg width=300>----><img src=img/StartLt.jpg width=300></div>

Click the LT button to enter the LT page:

<div align="left"><img src=img/LTInit.jpg width=300></div>

When someone speaks during the meeting, the LT transcript is displayed on the LT page:

<div align="left"><img src=img/LTSpeak.jpg width=300></div>

The LT page supports content search. Enter the content to be searched in the search box:

<div align="left"><img src=img/LTSearch.jpg width=300></div>

To the right of the search box is the LT control button, which can control the start and pause of the LT, visible only to the host or moderator:

<div align="left"><img src=img/LTControl.jpg width=300></div>

If LT is enabled, the LT button in the more menu changes to view transcription:

<div align="left"><img src=img/ViewLt.jpg width=300></div>

### 2.3 Lay Out

There are currently two layouts, gallery and active speaker. The default layout is gallery. When there are more than one person in a meeting, the layout selection button is displayed to select the appropriate layout. 

<div align="left"><img src=img/LayoutSwitch.png width=300></div>



#### 2.3.1 Gallery



This is the layout of the RCVUIKit-iOS main page. Sliding pages are adopted. Basic information of up to three participants is displayed on each page.  
Each participant has a corresponding cell in the gallery, used to display the participant of the video/audio/network/avatars and other information.

<div align="left"><img src=img/gallery.png width=300></div>



#### 2.3.2 Active Speaker

Display the active speaker in the middle. If no one is speaking, the first member who is not your own member is used by default. If the speaker changes, the screen switches. The video screen of the active speaker is displayed in the center area, and the network, audio, and name of the active speaker are displayed in the lower left corner.

<div align="left"><img src=img/ActiveSpeaker.png width=300><img src=img/SpeakerVideo.png width=300></div>



If local video is enabled, the image is displayed in the lower left corner of the lay out layout. You can drag to move the local video, or double click to zoom in (out) the local video.

The camera switch button<img src=img/cameraButton.png width=40> in the upper right corner of the local video screen allows you to switch between the front and rear cameras.

<div align="left"><img src=img/LocalVideo.png width=300><img src=img/LocalVideoMove.png width=300><img src=img/LocalVideoLarge.png width=300></div>

## 3.How to integrate RCVUIKit
### 3.1 Preparatory
The RCVUIKit-iOS component library implements the UI and business after successfully joining a meeting, so the application layer needs to finish the below tasks before the meeting:  
- Construction project   
  Add rcvsdk and RCVUIKit to the project:  

  <div align="left"><img src=img/framework.png width=700></div>

  Add the RCVUIKit resource pack(Resources) to the project

  <div align="left"><img src=img/resources.png width=700></div>

- Add rcvsdk and RCVUIKit to the project: 

- Create a RingCentral Client Video SDK instance  

- Start or Join a meeting
### 3.2 How to use RCVUIKit
The RCVUIKit component externally provides the RcvVideoMeetingViewer class, which is a UIViewController class.  
The APP layer only needs to display the RcvVideoMeetingViewer after start or join a metting. The example code is as follows:  

<div align="left"><img src=img/rcvMeetingViewer.png width=900></div>

## 4.How to screen share
[How to screen share please refer this link](./screenshare/README.md)