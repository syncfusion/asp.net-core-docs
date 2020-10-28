---
layout: post
title: Getting-Started
description: getting started
platform: aspnet-core
control: Presentation
documentation: ug
---
# Getting Started

## Creating a simple PowerPoint Presentation with basic elements from scratch

Refer the [Getting Started](/aspnet-core/getting-started) page of the introduction part to know more about the basic [system requirements](/aspnet-core/getting-started#system-requirements) and the steps to [configure Syncfusion File Formats components](/aspnet-core/getting-started#configure-syncfusion-file-format-components-in-aspnet-core-application) in an ASP.NET Core application.

Ensure whether all the following dependency packages are included within the project.json file as mentioned [here](/aspnet-core/getting-started#configure-syncfusion-file-format-components-in-aspnet-core-application), to create and manipulate the PowerPoint presentation using Presentation library.

<table>
    <thead>
        <tr>
            <th>
                Package Name
            </th>
            <th>
                Short Description
            </th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>
                Syncfusion.Presentation.AspNet.Core
            </td>
            <td>
                This package contains the core features needed for creating, reading, manipulating a PowerPoint presentation.
            </td>
        </tr>
        <tr>
            <td>
                Syncfusion.Compression.AspNet.Core
            </td>
            <td>
                This package is used to archive/extract the PowerPoint presentation contents.
            </td>
        </tr>
        <tr>
            <td>
                Syncfusion.OfficeChart.AspNet.Core
            </td>
            <td>
                This package contains the Office Chart Object model and core features needed for chart creation.
            </td>
        </tr>
    </tbody>
</table>

Include the following namespace in your .cs code as shown below

{% highlight c# %}

using Syncfusion.Presentation;

{% endhighlight %}

An entire PowerPoint Presentation is represented by an instance of IPresentation interface and it is the root element of Essential Presentation’s DOM.

The following code example demonstrates how to create an instance of IPresentation interface.

{% highlight c# %}

//Creates a new instance of PowerPoint Presentation

IPresentation presentation = Presentation.Create();

{% endhighlight %}

IPresentation instance has a slide collection that represents the individual slides present within PowerPoint Presentation. A slide may contain textual and other graphics contents like shapes, images, charts etc.

The following code example demonstrates how to add a blank slide to a PowerPoint Presentation.

{% highlight c# %}

//Adds a slide to the PowerPoint Presentation

ISlide firstSlide = presentation.Slides.Add(SlideLayoutType.Blank);

{% endhighlight %}

N> The “Point” typographic units are used to add or manipulate any element in a Presentation. 

All the textual contents in a Presentation document are represented by Paragraphs. Within the paragraph, textual contents are grouped into one or more child elements as TextParts. Each TextPart represents a region of text with a common set of formatted text.

The following code example demonstrates how to add text into a Presentation.

{% highlight c# %}

//Adds a textbox in a slide by specifying its position and size

IShape textShape = firstSlide.AddTextBox(100, 75, 756, 200);

//Adds a paragraph into the textShape

IParagraph paragraph = textShape.TextBody.AddParagraph();

//Set the horizontal alignment of paragraph
          
paragraph.HorizontalAlignment = HorizontalAlignmentType.Center;

//Adds a textPart in the paragraph

ITextPart textPart = paragraph.AddTextPart("Hello Presentation");

//Applies font formatting to the text

textPart.Font.FontSize = 80;

textPart.Font.Bold = true;

{% endhighlight %}

Essential Presentation allows you to create simple and multi-level lists that make the content easier for reading. The following code example demonstrates how to add a bulleted list in a paragraph.

{% highlight c# %}

//Adds a new paragraph with text.

paragraph = textShape.TextBody.AddParagraph("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");

//Sets the list type as bullet

paragraph.ListFormat.Type = ListType.Bulleted;

//Sets the bullet character for this list

paragraph.ListFormat.BulletCharacter = Convert.ToChar(183);

//Sets the font of the bullet character

paragraph.ListFormat.FontName = "Symbol";

//Sets the hanging value as 20

paragraph.FirstLineIndent = -20;

{% endhighlight %}

In PowerPoint Presentation, the multilevel lists are used for presenting the content in a hierarchy. You can create a multi-level list by setting the indentation levels. By default, the level begins at 0 and increments by 1 for each level. The following code example demonstrates how to add multi-level list in a paragraph.

{% highlight c# %}

//Adds a new paragraph  

paragraph = textShape.TextBody.AddParagraph("Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.");

//Sets the list type as bullet

paragraph.ListFormat.Type = ListType.Bulleted;

//Sets the list level as 2. Possible values can range from 0 to 8

paragraph.IndentLevelNumber = 2;

{% endhighlight %}

You can add images to the Presentation by adding them in the picture collection of a slide. The following code example demonstrates how to add an image in a presentation.

{% highlight c# %}

//Gets the image from file path

Image image = Image.FromFile("image.jpg");

// Adds the image to the slide by specifying position and size

firstSlide.Pictures.AddPicture(new MemoryStream(image.ImageData), 300, 270, 410, 250);

{% endhighlight %}

Finally, save the Presentation in file system.

{% highlight c# %}

MemoryStream ms = new MemoryStream();

//Saves the presentation to the memory stream.

presentation.Save(ms);

//Set the position to the beginning of the stream.

ms.Position = 0;

//Initialize the file stream to download the presentation.

FileStreamResult fileStreamResult = new FileStreamResult(ms, "application/vnd.openxmlformats-officedocument.presentationml.presentation");

//Set the file name.

fileStreamResult.FileDownloadName = "Sample.pptx";

{% endhighlight %}

The resultant PowerPoint Presentation looks as follows.

![](GettingStarted_images/GettingStarted_img1.jpeg)