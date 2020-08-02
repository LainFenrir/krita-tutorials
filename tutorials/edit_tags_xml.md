# How to tag brush presets by editing the XML tag file
While krita allows tagging for brushes, presets,palettes... one thing it doesn't allow is tagging multiple things at the same time. which can become a boring task when you have many brush presets to tag. One way to do this fast is directly editing the tag XML file, yet every time I suggest that to people they seem afraid to do that saying it seems troublesome or they are not tech savvy enough for that. So with this post I want to show people how easy that is.  

OBS:  want to make it clear that I didnt look into krita source code to see how the xml files are created so my explanation on how krita creates these files might be wrong, not that it makes much difference for the tutorial itself.  

## What is an XML file
An XML file is simply a descriptive file. It uses tags to separate the information inside the file, its similar to how html works and is used mostly to contain data. 

To understand what a XML file is doing you just need to read the tags there is always a starting tag `<tag>` and and a end tag `</tag>` and the information can be between the tags or as a tag attribute like `<tag param="value">something here </tag>` this is a basic XML structure. now lets take a look at krita's file for the paintpresets tags:  

![Code Exemple](/images/xml/File_exemple.png)

It may seem like a lot but lets breakdown this file.  

## Understanding Krita tags

```xml
<?xml version="1.0" encoding="UTF-8"?>`
<!DOCTYPE  tags>
```

these first 2 lines can be ignored, they are just the XML header they are just the document definition, we wont touch these.  

`<tags>` is where our tags will be stored, although not showed in the image, there is a  `</tags>` at the end of the document. All presets definitions are between these 2 tags.  

Now to the preset itself, it is defined in a resource structure, the `<resource>` tag is created by krita whevener you add a new paintpresset be it by a bundle, adding manually to the painttopreset folder, adding a painttopreset in the resource bundle. In short this structure will be given to you so don't worry too much about how its structured.  

```xml
<resource md5="KxrOypI+SgGmqsLe1cbc4w=="identifier="bundle://~/AppData/Roaming/krita/bundles/concept&amp;illustration.bundle:paintoppresets/5.Guides_ grid.kpp">
	<tag blacklisted="false">Concept</tag>
</resource>
```

The parameters inside resource are:
**md5** -  this is just to verify the integrity of the preset, nothing for us here.

**identifier**- this is what we need to look, it gives us the path of the preset, which can or cannot be useful, and the name of the preset in the end of the line `:paintoppresets/5.Guides_ grid.kpp"` this is how we know what preset this is and this is what we will use to search.

Then we have the most important line for us:
```xml
<tag blacklisted="false">Concept</tag>
```  

This is what defines the tag this preset belongs to, and the name of the tag that will appear in the dropdown menu in the paint presets docker.
so to the parameter:  

**blacklisted** - will define if the preset in question will appear in the tag or not. This is more for krita to handle, you can just erase the tag line in the file to take it out of the tag.  

So finally we have the name between `<tag>Name of your tag here </tag>`like stated before this will be the name it will be shown in krita.  


## How to edit it
First you need to find the file you want to change, and that is the `kis_paintoppresets_tags.xml` this file is located in the your krita resource folder in the folder tags.  

If you don't know how to get to this folder you just need to go to settings>manage resources and there you click `open resource folder` button.  

![Resource manager](/images/xml/Resource_manager.png)

Now you need a text editor, notepad is enough for this however I would recommend either vscode or notepad++ cause both of them have code highlight which is helpful.  

So open the file with your editor of choice, I use vscode just because its the editor I use for programming. Have this in mind as I dont know if the shortcuts are the same for other programs like notepad++.  

So for the preparation take notes of the preset names you want to tag, you can leave krita open to check the names or write them down beforehand.  
> if you have krita open you will need to restart it after saving the file so krita can load the new file.  

### Editing the file
first you need to look for the preset you want to change a simple <kbd>Ctrl</kbd>+<kbd>F</kbd> will bring up the search function now you just need to type the name of the brush or the name of the tag it belongs to and press <kbd>Enter</kbd> to search.  

In my exemple I will be searching for my tag `<tag blacklisted="false">Extra</tag>` so I type that in the search bar and it will find all the places this exist.  

![File Search](/images/xml/File_search.png)

Now you can just copy the tag line paste under the one that exists and change the name of the tag to the new tag you want. Like this:  
```xml
<tag  blacklisted="false">Extra</tag>  
<tag  blacklisted="false">Krita 4 ExRZV</tag>
```

In my exemple I want to create a new tag that combines the default krita 4 brushes with brushes of 2 other bundles [David Revoy extra brushes](https://www.davidrevoy.com/article742/krita-4-extras-brush-presets-pack) and [RZV bundle](https://razcore.gitlab.io/posts/2017/06/11/p02-rzv-krita-brushkit/). As you can imagine this would be a tiresome job to do. Well you can use the replace function of your editor.  

![Replace function](/images/xml/Replace_button.png)

In my exemple i will search for `<tag blacklisted="false">Extra</tag>` and will replace it for:  

```xml 
<tag blacklisted="false">Extra</tag>
  <tag blacklisted="false">Krita 4 ExRZV</tag>
```
I am replacing it for the same thing plus the new tag I want, what this will do is create a new line with the new tag and I can just press for it to replace all instances and I am done, in part. I would need to repeat this process with the other 2 tags too but its much faster than doing it manually through krita.  

You must have noticed the 2 spaces on the second line, those are just to indent the code correctly not really necessary but I like my code nice and clean.  

And now I just need to save the file, open krita and here is my new tag with all the brushes.  

![Replace function](/images/xml/Result.png)

I hope this helped people to find new ways to organize their brushes faster and broke a bit of the fear of editing files. 

