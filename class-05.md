Images-->

every website must have images, images do a lot about the website, and they help attract users' attention.
when we want to add images in html file it's beeter to add a folder to put all images in it, then insert it in html through path of the folder.

to insert images in html we use < img > element (and it's a self closing tag), there is an attributes using with img tag like: src-> using this attribute to tell the browser where can find the image file
       alt-> provides a text description of the image to descripe it when the image broken
       title-> using title to provide additional information about the image.
       height/width-> to specifies the height and width of the image in pixels.

can add the images in code( before a paragrapg, inside the start of a paragraph, in the middle of a paragraph)

there is a three rules to create image:
1)should save it in the right format (jpeg ,gif,png)
2)should save it at the right size (the same width and height it will apper in website 
3)should use the correct resolution(refer to the number of dots per inch)

**using jpeg format for the images that coontain natural scene, png in any image need transparency and gif for imges that contain animations

**compression : use it to reduce the size of data and insure faster transmission. 1) lossy 2)lossless

lossless--> it is possible to reconstruct the original image from the compressed image because there is no information loss during compression
lossy-->data loss is irreversible

**transparency--> indicates something that is completely invisible

the jpeg is lossy compression,don’t support transparency
 png ia a lossless (use deflate compression)  support transparency
 
Color-->

Every color on a computer screen is created by mixing amounts of red, green and blue

in CSS can spescify color in many ways (RGB, HEX and Color name) -RGB VALUES: values for red, green and blue are expressed as number between (0-255) HEX CODES: represent values for red, green and blue in hexadecimal code -COLOR NAME: represented by predefined names

-HSL COLORS (CSS3 used this way to specify colors) : also color have a HUE, SATURATION AND BRIGHTNESS values HUE->colloquial idea of color (represented as a color circle and the angle representes the color OR shown as a slider with values (0 - 360)

SATURATION-> the amount of gray in a color (max: no gray, min: mostly gray) represented as a percentage (100% full , 0% shade)

BRIGHTNESS-> the amount of black in a color (max: no black, min: very black) represented as a percentage (100% lightness is white ,50% lightness is normal , 0% lightness is black)


Text-->
there is alot of properties that allow to control the appearance of text,
there is a Typeface Terminology for text  like (SERIF, SANS-SERIF, MONOSPACE) and these terminology display only if it is installed on tha user's computer, 
Also there is a properites like width of the text, style (normal,Italic) and stretch.
there is a techniques that offer a wider coice of typefaces like (font-family, font-face, service-based font -face).

type scales->
you can use a different units of type size like (pixels, percentages, ems)

and there is alot of propertis can used to style text like (font-weight: bold , font-style: italic, text-transformation: lowwer/uppercase), leading(line-height))
also can add something on links like (:link, :visited.. etc)

