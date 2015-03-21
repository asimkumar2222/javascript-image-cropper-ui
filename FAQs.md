# Introduction #
This section covers any frequently asked questions, I will slowly build this list up as I see regular questions arise.

# 1. How do I save the cropped image? #
The JavaScript Image Cropper UI is simply a JavaScript interface to allow a user to select the area of an image they wish to crop. Physically cropping and saving the image is beyond the abilities of JavaScript and should be performed server-side, this usually works in the following process:

  1. User uploads image
  1. Cropper is displayed
  1. User selects area to crop and submits a form
  1. Server crops and saves the image (may also resize - e.g. for a fixed size avatar)
  1. Present user with the cropped and saved image

## 3rd Party Server-Side Implementations ##

There are some 3rd party server-side implementations that work with the JavaScript Image Cropper:

**PHP:**
  * [Tutorial for using with PHP (30th Dec 2009)](http://www.londatiga.net/it/how-to-crop-image-using-javascript-and-PHP/)
  * [http://www.theatons.com/php-js-image-cropper](http://www.theatons.com/php-js-image-cropper)
  * [http://mondaybynoon.com/2007/12/17/crop-and-resize-images-with-gd-or-imagemagick-v11/](http://mondaybynoon.com/2007/12/17/crop-and-resize-images-with-gd-or-imagemagick-v11/)

**Coldfusion:**
  * [http://cfsilence.com/blog/client/index.cfm/2007/8/2/Introducing-cfImageCropper--Custom-Tag-For-Client-Side-Image-Cropping](http://cfsilence.com/blog/client/index.cfm/2007/8/2/Introducing-cfImageCropper--Custom-Tag-For-Client-Side-Image-Cropping)

**.Net && C#:**
  * [Code and tutorial for using with .Net && C#](http://geekswithblogs.net/SanjayU/archive/2008/09/08/asp.net-image--photo-cropper-in-c.aspx)

(Note if you have a server side implementation of the cropper which not listed above please contact us via the [Google Group](http://groups.google.com/group/javascript-image-cropper-ui)



# 2. How do I prevent the user from re-sizing the cropper #

You can prevent a user from re-sizing the cropper on either a single or both axes by setting the min dimension & max dimension to the same value - this will make the cropper not display the appropriate resize handles, e.g.:

  * Set `minWidth` and `maxWidth` to same value and the user will not be able to change the width.
  * Set `minHeight` and `maxHeight` to the same value and the user will not be able to change the height.
  * Do both of the above and the user will not be able to resize the cropper at all.

# 3. How do I crop a very large image #

The best way to crop a very large image is to reduce the size of the image before cropping (e.g. from 2048x2048 to 600x600) and present the resized image to the user for cropping. Then for best results you'd translate the crop co-ordinates from the small size and use the original as the source for the actual cropping to be performed (for the above example you'd multiple all crop the dimensions by 3.413333333).