# Publishing from Stage TEN to OBS Studio
*An unofficial guide for using Stage TEN output as a video source in OBS*

## Overview
Premium plans allow embedding Stage TEN output into third-party websites or OBS Studio. This embed code is available in the Stage TEN destination settings.

## Setup Process

### 1. Getting the Stage TEN URL
- Find the embed code in Stage TEN destination settings
- Extract only the URL (e.g., `https://play.stageten.tv/embed/XXXXXXXAAAABBBBYYYYYYYYY`)
- Opening this URL in your browser will show the Stage TEN output with chat sections and other components (these will be removed in OBS)

> **[UPDATE: Feb 11th 2025]**  
> Use the SDK URL instead: `https://play.stageten.tv/sdk/2023-03/channel/XXXXXXXAAAABBBBYYYYYYYYY`  
> This provides cleaner video output with auto-playing audio, preferred until a dedicated clean URL option is added.

### 2. Going Live in Stage TEN
1. Start your Stage TEN broadcast
2. Select "Stage TEN Interactive Player" as the destination
3. The video output should now be visible in your browser

### 3. OBS Configuration

#### Creating the Browser Source
1. In OBS, add a new Browser source
2. Enter your Stage TEN URL in the URL field
3. Configure the dimensions:
   - For 16:9 landscape: Width `1920`, Height `1080`
   - For 9:16 portrait: Width `1080`, Height `1920`
4. Enable "Control audio via OBS"

#### Important: Video Playback
If you see a play button in OBS for this browser source:
1. Right-click the source
2. Select "Interact"
3. Click the play button to start the video

#### For Embed URL Users Only
If using the embed URL (not SDK), add this Custom CSS to remove extra elements:

```css
div{background-color:#0000!important;}
section{width:0;height:0;background-color:#0000!important}
div>video{margin:0 auto!important;width:100vw!important;height:100vh!important;;position:fixed;top:0!important;right:0!important;display:block!important;background-color:#0000}
video{width:100%!important;height:100%!important;display:block;margin:0 auto;padding:0;background-color:#0000!important;object-fit:contain!important}
[class*="mainView_sidePanel"],[class*="MobileVideoOverlayLaye"], [class*="DesktopVideoOverlayLayer"], .animation-target, h2, [class*="UnmuteButton_unmuteButtonText"] {display:none!important;}
```

## Working with the Stream

### Video Control
- Stopping Stage TEN output will stop the video in OBS
- Starting Stage TEN and selecting "Stage TEN Interactive Player" will resume the video
- Settings persist after initial setup
- You can apply any overlay to this video in OBS
- Guests in Stage TEN will see the video without OBS overlays

### Stream Management
- Stream continues uninterrupted if Stage TEN studio control transfers between guests
- OBS operator needs stable, wired internet connection
- Can switch between multiple Stage TEN outputs mid-stream
- Only stopping OBS publishing will interrupt the stream
- Possible to switch between different Stage TEN outputs mid-stream without interruption

## Additional Features

### Text Sharpness Enhancement
To improve text clarity:
1. Right-click the browser source
2. Select "Filters"
3. Add a "Sharpen" effect filter
   - Use minimally - a little goes a long way
   - Primarily helps with text and overlay clarity
   - Not needed for most types of content

## Support
Premium users can contact Steve on the [Stage TEN Discord](https://discord.com/invite/y2yKVBm) for setup assistance. Note that this is an unofficial feature and access may change.
