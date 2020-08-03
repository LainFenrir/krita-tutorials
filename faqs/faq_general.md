# General Faq
A reminder, krita has its own [Official FAQ](https://docs.krita.org/en/KritaFAQ.html) and I encourage you to look at it.

## 1. Very general questions

### How do I update krita? / Does Krita auto update? / Can I update krita from the program?
Just go to krita website and download the newest version, and install it(no need to uninstall the older version cause the krita installer will handle that).
Krita doesn't have any sort of auto update or anyway to update the program from itself, you need to download the new version yourself.

The Exceptions to this are the steam and microsoft store versions, however this is more a consequence of the stores auto update when a new version is out. its not any sort of locked feature.

### Is there any difference between the paid versions to the free version?
Nope, its the exact same program. The paid versions is just a way to give some money to the krita development.

### What is the difference between protable version to the installer?
None, other than the portable you dont need to install it.

### If I update krita will I lose my drawings and/or my brushes and settings?
No.

### How do I share things I made in krita? / How to export images?
In the menu on the top, go to `File>export` and choose a format, the most common ones are png and jpeg/jpg. I reccomend png over jpeg though, it will keep the quality of your image even if you set the compression to max, jpeg on the other hand...the more compressed worse the quality.

### Krita lags when i try to paint what to do?

### I cant draw on the canvas anymore
This can mean many things usually it's a selection active, just deslect everything.

### How do I deselect something?
<kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>a</kbd>

### How to import brushes?

### How to turn snapping off?

### I press the pen down and a weird brush thing appears / Holding the pen on the canvas shows up the popup palette
That is a Windows related issue.

### My tablet is not working well in krita

### I try to open my file in krita and it says it cant open it or that its corrupted, How to recover the file?

### What is the shortcut for ____?
In the menu on the top, go to `Settings>Configure Krita..` go to `keyboard shortcuts`, It has a search bar that you can look for the action or the shortcut itself.

### Can I open krita files in other programs? How to pass a krita file to another program keeping the layers?

### Krita keeps crashing when starting


## 2. Tools related Questions



### Why I cant undo anymore? I am pressing ctrl+z and its not working. / How to change the limit of undos?

### I try to fill an area of my drawing and fill bucket fills everything

### How to scale/resize something keeping the aspect ratio

### How to avoid the brush strokes to overlap each other?

### How to get rid of white border when using the fill bucket?


### How to make a text curve using vectors?
You can't, the text tools dont allow for you adjust the text like that. You can try converting the text layer to a paint layer and adjust there but honestly, Inkscape would probably be easier for that.

## 3. Dockers Related questions

### A docker disappeared how to bring it back?
In the menu on the top, go to `Settings > dockers` and find the docker you want and jsut click on it.

### How to move a docker/ how to stack dockers?

### How to undock a docker?


## 4. Layers related Questions

### How to use alpha inheritance?

### How to use the colorize mask?

### How to move/transform multiple layers at once

### How to transform a vector layer to a paint layer?


## 5. User Interface Related Questions

### An item disappeared from the topbar how to bring it back?

### Can I remove things from the toolbox or change the order?


---
## Feature FAQ

### Does krita have a selection brush like Paint Tool Sai?
No.

### Can I change the line weight in some parts of a vector like in paint tool sai?
No, use a program like inkscape for that.

### Can I import photoshop brushes?
Yes and no. Krita only allows to import the brush tip image, not the brush settings. So once you import the brush inside krita, it will be stored as a brush tip.
For you to be able to use it you will need to select a brush preset in krita and change the brush tip to the tip you imported. For the settings there is no easy way to port a brush from photoshop to krita, you will need to to experiment with the brush engine.

### Does Krita has a stabilizer/correction function like Paint Tool Sai or Medibang Paint Pro/Fire Alpaca?
Yes and no. Krita offers some smoothing settings for the brush tool, that includes the stabilizer, that is a way to stabilize your stroke.
It also has the dynamic brush tool that is another brush tool that can be used to stabilize your strokes. 
However, both work differently from Medibang Paint Pro or Sai, in these programs the line is corrected after you finished it depending on the correction level, krita doesn't do that.

### Does krita have clipping mask?
Yes and no. Krita has the alpha inheritance, which gives very similar results but its not exactly a clipping mask.

---
# Animation FAQ

### How to activate onion skin?


### How to export animation? / How to export animation as a video or gif?
I Made a whole tutorial for this, including how to set FFmpeg(on windows only) you can see it [here](../tutorials/ffmpeg_krita_windows.md) .

### How to export a transparent gif?
Short answer is you cant. you need to export as a image sequence (make sure to use a format that allows transparency like png) and assemble as gif in another program, for info on how to export as a image sequence check [here](../tutorials/ffmpeg_krita_windows.md) 

### How to move the contents of one frame to another?

### How to move multiple frames at once?

### How do I create a tween in krita?

### Does krita have a camera function for animation?

---

# Plugin FAQ/ Python Scripting FAQ