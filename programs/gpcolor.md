---
title: GPCOLOR
layout: default
---

GPCOLOR changes the color components of color numbers
        on color devices where the components can be set.  See the
        help information on COLORS for more information.



# Input Parameters
 
	COLORS    Color list
	DEVICE    Device|name|x size;y size|color type
 


# Examples
 
Set color number 4 to violet.

    COLORS  =  4=violet

Set color number 2 to yellow by specifying the red, green,
and blue components.

    COLORS  =  2=1:1:0


# Error Messages
 
	[GPCOLOR  -1]   Fatal error initializing TAE.
	[GPCOLOR  -2]   Fatal error reading TAE parameters.
	[GPCOLOR  -3]   Fatal error initializing GEMPLT.
