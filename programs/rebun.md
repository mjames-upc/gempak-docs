---
title: REBUN
layout: default
---

                                                                   
REBUN accepts a VGF file containing any number of watch elements and
generates a 6-sided polygon generally representing the area covered by
the counties listed in the watch. This polygon will be written to 
another VGF file named `rebun.vgf`.

# Input Parameters

    rebun input_vgf_filename expand

* `input_vgf_filenam`	VGF file containing watches
* `expand`		Expansion flag (0-FALSE,1-TRUE)
    
    If TRUE, the 'expand' parameter will adjust the sides of the
    resulting polygon to include all county centroids.
	                                                                   
# Program Description

REBUN scans a VGF file for watch elements and calls the function
`rebundle` for each one it finds.


# Examples

    rebun input.vgf 1

processes all watch elements in the file `input.vgf` and
applies the expand option. Output is to file `rebun.vgf`.

