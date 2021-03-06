---
title: NFAX
layout: default
---



NFAX displays NMC 6 bit raster fax products.


##  LOADING A PRODUCT

A product is displayed by selecting "File" from the menu, and "Load Product" 
from the pull down menu.  A popup dialog box prompting for entry of a wheel 
number is displayed.  The dialog box contains a radio box of choices that 
equate to specific times along the creation path of the product.  Currently 
only "Local pre 6 bit" and "Local 6 bit" are available.  The pre-6bit version 
of the product is an uncompressed black and white raster representation of 
the product.  Selecting "Local pre 6 bit" displays this uncompressed version.  
The "Local 6bit" product is produced by compressing the raster representation 
of the product into a run length encoded product that is transmitted over 
DIFAX circuits.  Viewing the Local 6bit product decompresses the 6 bit product 
to a raster image and displays it on the screen.

The wheel dialog is completed by obtaining the configuration information from 
the product table.  This information is retrieved by entering the wheel number 
for the product in the form, then pressing the "Read Config" button.  If a 
valid product has been entered, the title of the product is displayed in the 
"Description:" field.

After the configuration for the product has been retrieved, select the OK 
button to display the product.

##  SUBSAMPLING A PRODUCT

Because the NFAX display area presents products in a 1 product pixel per 
display pixel ratio, most products must be scrolled to view the entire product. 
Scrolling can be avoided by loading the image in a subsampled mode.  To load 
an image in a subsampled mode, select the "Sampling" option from the "Settings" 
menu.  Choose either 1:1, 1:2, 1:3, or 1:4.  In a 1:4 sampling mode, for 
example, the product is displayed where one screen pixel represents four 
product pixels.

## CLEAR SCREEN

Select "Clear Screen" from the Edit menu pulldown to clear the display area.
