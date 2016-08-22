---
title: GD2IMG
layout: default
---

GD2IMG creates a GINI format image from a grid. The GINI image
   format allows only a limited number of projections, with
   pixels containing the same dx and dy values. Only Lambert
   tangent conic conformal projections are possible 
   (eg `Latin1 = Latin2`). Users must ensure that the grid area 
   specified meets these limitations.


# Input Parameters
 
	GDFILE    *Grid file
	GDATTIM   *Grid date/time
	GLEVEL    *Grid level
	GVCORD    *Grid vertical coordinate
	SCALE     *Scalar scale
	GFUNC     *Scalar grid
	PROJ      *Projection of output satellite image
	GRDAREA   *Area for output image
	KXKY      *sampled image resolution
	CPYFIL    *May be used to provide image navigation
	SATFIL    *output image
 
 
# Program Description

 
# Examples
 

# Error Messages
 
    None
