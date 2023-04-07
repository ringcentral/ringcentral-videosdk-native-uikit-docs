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

#### 2.2.4 Screen Sharing Action
#### 2.2.5 Meeting Recording Action
The recording button<img src=img/startRecord.png width=40> will be displayed in the Meeting Bottom Bar if your account has recording rights, otherwise it will not be displayed. With this button you can control start/pause/resume  recording. 

<div align="left"><img src=img/record.png width=300><img src=img/pause.png width=300><img src=img/resume.png width=300></div>

### 2.3 Gallery 
This is the layout of the RCVUIKit-iOS main page. Sliding pages are adopted. Basic information of up to three participants is displayed on each page.  
Each participant has a corresponding cell in the gallery, used to display the participant of the video/audio/network/avatars and other information.

<div align="left"><img src=img/gallery.png width=300></div>

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