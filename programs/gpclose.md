---
title: GPCLOSE
layout: default
---

GPCLOSE closes the graphics output window or file
specified in the DEVICE parameter.

# Input Parameters
 
	DEVICE    Device|name|x size;y size|color type
 
 
# Examples
 
	DEVICE	= xw|window2

# Error Messages
 
	[GPCLOSE  1]   Cannot close window. Blank name is invalid.
	[GPCLOSE  -1]   Fatal error initializing TAE.
	[GPCLOSE  -3]   Fatal error initializing GEMPLT.
