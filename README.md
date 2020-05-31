OpenType-SVG color fonts
⇑
¶
What's inside color fonts?
A color font file is actually just a regular font file that embeds additional data to display more graphic properties than the contour shapes of a character.

Color fonts are now generally stored as SVG data inside OpenType font files. This SVG (Scalable Vector Graphics) format can hold vector shapes with color or gradients, and may also include bitmap images - thus leading to bitmap fonts.
So color fonts are now officially referred as OpenType-SVG fonts.

Simple. Right?
OpenType-SVG logo
Ok, the reality is a bit more complex...
#TimeForSomeHistory ;)

The OpenType-SVG font format was initially designed by Mozilla & Adobe and became an industry standard in early 2016, when other big players including Microsoft & Google agreed on a single format to support color fonts. 

All of them (including Apple) have previously developed and implemented their own proprietary color formats to display emojis on their operating systems, while many other companies built other custom color font technologies for the gaming, video or print industries.

There are now four major color font formats that fit into regular font files: SBIX, COLR, CBDT and SVG, each having it own specificities. Read the full story here or check this simplified recap:
	Vector 	Bitmap 	Native support
W3C SVG 	✔ 	✔ 	macOS 10.14+, iOS 12+, Windows 10+
Apple SBIX 		✔ 	macOS and iOS
Google CBDT 		✔ 	Android
Microsoft COLR 	✔ 		Windows 8.1+
Due to the differences and incompatibilities of these formats, the design industry is going through a transition period during which several color font formats may be needed to ensure cross-platform compatibility across several operating systems, browsers and apps.

But OpenType-SVG seems in great position to become a golden standard now that three operating systems support OpenType-SVG fonts: Windows 10, macOS Mojave, and iOS 12.

A solution to mitigate this issue on legacy software? Color fonts can also include some alternate vector shape data as a fallback solution for software that do not (yet) support any of the embedded color formats.
⇑
¶
Where's the catch?
What about file size?
A color font file is generally larger than a regular font file, and a lot more when the font embeds high-resolution bitmap characters.

Whereas fonts usually weigh tens to a few hundred kilobytes, color vector fonts can reach hundreds of kilobytes to a couple megabytes depending on their visual complexity.

Color bitmap fonts may range from a few megabytes to tens of megabytes, and sizes increase when multiple color font formats are embedded in a single file.

What about text scalability?
Good question! Color fonts based on vector glyphs can be resized without any loss, just like any regular font.
Scaled color vector font
Scaled color vector font
Scaled color bitmap font
Scaled color bitmap font
Color bitmap fonts, like any other photo or pixel-based image, will scale properly up to a certain size, depending on their original resolution. Beyond that resolution, the lettering will look pixelated.

So whether you print a text with a color bitmap font or display it on high resolution screens, you will have to check up to which size it could properly scale.

As color bitmap fonts will be used in such different contexts like web or print, designers will need several versions
