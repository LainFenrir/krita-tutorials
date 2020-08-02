
# Rendering animation in krita (Windows)

One of the most asked questions I see about krita is how to export animation as a video or gif. Krita has a [documentation](https://docs.krita.org/en/reference_manual/render_animation.html) but I feel like it could use some images to make things easier to understand.  

I also encourage you to read this post to this end for reasons why you shouldn't render video in krita and some useful tips.  

> Krita version at the time of this tutorial was made was 4.2.8

## Downloading FFmpeg
Krita uses ffmpeg to render video just like many other programs but it doesn't come bundled with it. You need to download it separately.  

Windows users will need to download the [zeranoe build](https://ffmpeg.zeranoe.com/builds/). The website is very straight forward you need to choose your version, your system architecture and the type of linking.   

![Zeranoe builds website](/images/ffmpeg/Zeranoe_builds.png)

The problem I see the most is people downloading the wrong version. These are the steps for downloading: 
1. For version you will want to download the stable version ( 4.2.1 at the time I took the screenshot). 
2. Select your operating system (if in doubt select Windows-64 bit). 
3. Linking needs to be static for it to work.
4. After selecting all these press the `Download Build` button.

If you download the build with something selected wrong it will not work in krita.  

After  downloading it unzip it anywhere in your PC. Now you need to copy the path to the `ffmpeg.exe` file. Inside the folder you unzipped, go to the `\bin` folder.  

![Inside the bin folder you will have these files](/images/ffmpeg/FFmpeg_folder.png)

Copy the full path to this folder, now we need to get inside krita.  

## Setting up FFmpeg
 For some weird reason, the path to ffmpeg is set inside the the dialog to render animation, this is under `File> Render Animation...`  

 ![Render Animation in the menu](/images/ffmpeg/Menu_render.png)

 The problem with this, is that this option will be disabled unless you have at least one frame set up, so just create a frame with anything in it like I did so you can access the render animation dialog box.  

 ![Render animation dialog box](/images/ffmpeg/Set_path_ffmpeg.png)

 Here make sure you have the video option on the top selected, and paste the path you copied, making sure to add  `\ffmpeg.exe` at the end of it. Or click in the folder icon to search for where is your unzipped folder in your system and select `ffmpeg.exe`. Both will work I just find copying and pasting faster.  

After this you are ready to render animations to video and gif. Once you have set the path you don't need to do this again.  

## Render in Krita
Krita gives you 2 different modes to export your animation, video or image sequence, it also gives you the option to export both at the same time.  

### Video/GIF
> **Important:** Krita doesn't support transparency in videos and gif format. If you try to export a file with transparency it will fill it with a color.
> To create a transaprent gif you will need to export as a image sequence, with a image format that allows transparency (png is a good one) and assemble that in another program

Under the video export option, you have the `Render as`drop down there you can choose the different possible formats you can export to.  

![Different formats to export as video](/images/ffmpeg/Choose_format.png)

Depending on the format you choose you will be able to access more export options pressing `...` button.  

![More export options](/images/ffmpeg/More_Export_Options.png)

If these doesn't make sense to you, the defaults work fine. That being said, an actual video editor might be better to change these options. 

#####  Settings
There are many settings in this dialog box, and while some seem intuitive like FPS I wanted to give a quick overview:  

**Frame First/Last**  
Sets the range of the frames that will be exported, if any frame is out of this range it will not be exported.   

**Height/Width**  
I can't seem to find information about this in the documentation but I can only assume it will change the resolution of the exported file to the one set here, by default it has the size of the canvas.  

**Video Location**  
The location the video will be exported to, by default it is set to `.\<filename>.extension` the `.\`means it will be in the same folder as the `.kra` file.  

##### Playing your animation
At the time of this publication, animations exported in krita do not work with Windows Player, they display a black screen, but the animation is exported fine. I suggest using another player like VLC to see the exported animations, or export in a video editor.

### Image sequence
> **You don't need FFmpeg to export as an image sequence**

It will export the each frame as an image, keep in mind layers will be flattened for this.  

![image sequence dialog box](/images/ffmpeg/Image_sequence.png)

##### Settings
Just like video, there are some settings I want to give a quick explanation. 

**Base Name**  
The default is `frame` meaning all the exported images will have the same name, this will be suffixed with the frame number so the file name will end as `frame0000.png`  

**Starting number**  
By default the frames start at 0, but some programs have trouble with this. So you can set a start number that will be increased at each frame.  

**Image Location**  
Same as video location, but keep in mind you will end up with many images so its good to create a new folder to put them in.  

![The formats for image sequence](/images/ffmpeg/Image_formats.png)

### Some tips for rendering animation

If I sum up all the tips I have in one sentence it would be "Be aware of your file size." Once your file size reaches over 2GB krita may start struggling to open it, going over that krita might crash trying to load your file leaving you with a unusable file. So these are my tips:

**Do not do everything in just one file**  
Once again if your file gets to big krita will struggle to open it. Krita is not toonboon or opentoonz where you have everything in one project file, its just not made with this workflow in mind. Krita works much better with a traditional animation, frame by frame workflow.  

**Separate your animation in scenes**  
Once again the problem is the file size. Keeping your scenes as different files will help you a lot if you have a huge animation.  

**Put audio or music using a video editor**  
Audio in krita is an unfinished feature made only to help in lip syncing, other than helping during the animation process, should not be used.  

**Dont use krita to render full animations**  
Please, DO NOT try to do this. I don't even recommend it for small animations. I have seen people trying to compose their whole animation using krita timeline putting background, tweening, sound and struggling to export. It never ends well, use a video editor for that or opentoonz.  

## Do you really need to render your animation inside krita?
Short answer is no. Unless you want to preview an animation or show an animation test to someone you shouldn't use krita to render your animation. I recommend exporting your animation as a image sequence and using a video editor to assemble your frames. this will give you much more control over your animation and will allow you to add some effects easier. There are many free video editors like Kdenlive, HitFilm, Blender, OpenShot and so on.. they are very easy to find online too.

There are many reasons to why I think rendering in krita is a bad idea, but the major one is the program is not made for this. Its better to use more than one program and having a better control over the whole process than insisting on using one for everything and struggle during the process, if you really just want to use one tool I recommend using opentoonz or Pencil2D.

## Conclusion
Although I am teaching how to render in krita, I don't really recommend relying on it to render animations other than showing animation tests or wips.

Krita is an amazing software but it has its limitations. I believe krita is amazing for animations in a traditional sense. For an idea of how to work with animation on krita, I suggest looking at [Ed tadeo videos](https://www.youtube.com/embed/rnBloU7cYpM).


