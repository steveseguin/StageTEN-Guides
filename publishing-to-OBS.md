# How to publish from Stage TEN into OBS Studio

This is an unofficial guide on using the main Stage TEN output as a video source in OBS

### Going from Stage TEN main output into OBS Studio

While not available to the free-tier plan, the premium plans allow for embedding the output of Stage TEN into a third-party website, such as your own website, or even into OBS Studio with some tweaking. This embed code is available in the Stage TEN destination settings.

<img src="https://user-images.githubusercontent.com/2575698/203494522-90279f82-b99b-44f6-9851-90000c7a6835.png" height="170" />

Since we are adding this video to OBS though, and not a website, we only want to grab the URL (https://play.stageten.tv/embed/XXXXXXX-AAAA-BBBB-YYYYYYYYY) from the embed code; not the entire code block.

<img src="https://user-images.githubusercontent.com/2575698/203493911-7b225b92-81a4-40f9-ba47-d51738253aad.png" height="250" />

We can then go live in Stage TEN, selecting the Stage TEN Interactive Player's output as the destination. 

<img src="https://user-images.githubusercontent.com/2575698/203497924-8e9371fc-9098-4409-883d-857fc99e0bbb.png" height="170" />


If we open the URL we extracted from the embed code now in our browser, we should see the output of Stage TEN.  There might be a chat-section and some other components visible, but we can remove those once we add the video to OBS in the next steps.

<img src="https://user-images.githubusercontent.com/2575698/203493652-d81e92f9-e21e-4489-9273-3b8f4863cd16.png" height="170" />


In OBS, we want to create a Browser source. This is just like adding a video device to OBS, but from the menu of options, we select `Browser`.

<img src="https://user-images.githubusercontent.com/2575698/203499296-b34b0a08-7d0f-4948-b2f8-8058c18e2aed.png" height="250" />

In the browser source settings, let's add our Stage TEN embed URL to the URL section.

Let's also ensure the Width is set to `1920` and the Height is set to `1080`.

We then need to to check the box `Control audio via OBS`, otherwise the stream's audio won't be captured by OBS.

Lastly, to remove the Stage TEN chat box and other styling effects, we need to add the following to the `Custom CSS` field in the OBS Browser source:
```
div{background-color:#0000!important;width:0;height:0}
section{width:0;height:0;background-color:#0000!important}
div>video{margin:0 auto!important;width:100vw!important;height:100vh!important;z-index:9999!important;position:fixed;top:0!important;right:0!important;display:block!important;background-color:#0000}
video{width:100%!important;height:100%!important;display:block;margin:0 auto;padding:0;background-color:#0000!important;object-fit:contain!important}
```

The end results should look a bit like the following:

<img src="https://user-images.githubusercontent.com/2575698/203493136-7c850584-4936-46cc-976b-e27c6e3cd9df.png" width="350" />

We should now be able to see our Stage TEN output as a clean isolated video source in OBS, with very little delay.  If we stop the output of Stage TEN, it will also stop the video going into OBS Studio. If we go live in Stage TEN again, and select the `Stage TEN Interactive Player`, the video will appear in OBS again.  Once this has been setup, we do not need to reconfigure the settings, making the initial setup a generally one-time ordeal.


<img src="https://user-images.githubusercontent.com/2575698/203503355-5e535be4-810b-4f47-ab9f-bd56465c85bd.png" width="550" />

We can apply any overlay we want on to this video in OBS, dynamic or otherwise, and then publish our OBS video mix to Youtube.

Guests within Stage TEN will see the video as well, minus any overlays that were added in OBS.

Whoever is managing OBS in this setup simply needs a stable and wired Internet connection, and the ability to start/stop the stream before and after the Stage TEN video itself starts and stops.

If at any point control of the Stage TEN studio needs to be transferred to a different guest, or the studio needs to be restarted, the output to Youtube itself will not be interrupted in this setup. Only if OBS stops publishing will the stream stop.  It would be possible to even switch between two different Stage TEN outputs in OBS, allowing for one creator to take over for another creator mid-stream, without the show being interrupted.


##### Support
Premium users of Stage TEN can Ping Steve on the Stage TEN Discord server at https://discord.com/invite/y2yKVBm for live help with this feature and setup, although please understand it is not an official feature offered by Stage TEN and it's access may be removed at any time

