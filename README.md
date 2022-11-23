# stageten_guide


Ensure you check the box `Control audio via OBS`, otherwise you might get echo or no audio capture in OBS.


To remove the Stage TEN chat box and other styling effects, we need to add the following to the `Custom CSS` field in the OBS Browser source:
```
body{background-color:rgba(0,0,0,0);margin:0pxauto;overflow:hidden;}div{background-color:#0000!important;width:0;height:0;}section{width:0;height:0;background-color:#0000!important;}div>video{margin:0auto!important;width:100vw!important;height:100vh!important;z-index:9999!important;position:fixed;top:0!important;right:0!important;display:block!important;background-color:#0000;}video{width:100%!important;height:100%!important;display:block;margin:0auto;padding:0;background-color:#0000!important;}
```

![image](https://user-images.githubusercontent.com/2575698/203493136-7c850584-4936-46cc-976b-e27c6e3cd9df.png)

