# Creating a Satellite Composite Basemap

This example utilizes the land/sea bitmask provided as a grid function within GEMPAK grid diagnostics. The resolution of the bitmask is 0.5 degree, and is adequate for the resolution of the N. Hemispheric Composite satellite product.


1. **Convert current IR satellite image to grid using IMG2GD**

	    PROJ     = STR/90;-105;0
	    GRDAREA  = -21;-150;-21;30
	    KXKY     = 800;800
	    GRDNAM   = irsat
	    GDFILE   = nhem_sat.gem
	    GLEVEL   = 0
	    GVCORD   = none
	    GDATTIM  =
	    CPYFIL   =
	    MAXGRD   = 200
	    IMGTIM   = last
	    CALIMG   = no
	    IMGFIL   = NHEMMULTI_IR
	    GEMPAK-IMG2GD>r
	    satellite image date/time 070530/1200
   
2. **Create a composite image satellite and land/sea mask using GD2IMG**

	* Use IRSAT values where brightness value is greater than 112 (eg 113 to 255, or colder than 0C). Subtract 112 from pixel values to produce values from 1 to 143 and set remaining values to 1.
	* Create a 0/1 boolean grid of land/sea.
	* Multiply the boolean 1/0 grid by 143 and add to the transformed IRSAT values as above.
	* The result is a grid of values ranging from 1 to 143 over land and 144 to 286 over the ocean.
	* Store the image as a gini image (Polar Stereographic projection 800 x 800).
	* Use a calibration range for band 10 for colors 0 to 94 representing pixel values 0 to 286.
	
			GDATTIM  = last
			GDFILE   = nhem_sat.gem
			GLEVEL   = 0
			GVCORD   = none
			SCALE    = 0
			GFUNC    = add(mul(bool(sea),143),miss(sub(sle(sgt(irsat,112),255),112),1))
			PROJ     = STR/90;-105;0
			GRDAREA  = -21;-150;-21;30
			KXKY     = 800;800
			CPYFIL   =
			SATFIL   = COMP_YYYYMMDD_HHNN
			CALINFO  = 99/10/SAT,0,94,0,286
			WMOHDR   = TICZ99/CHIZ/
			GEMPAK-GD2IMG>r
   
3. **Create a color lookup table**

	Create a lookup table representing land, ocean, and shades of IRSAT clouds for the 2 ranges of data above. 
	
	The color values 0 to 94 will be divided into 2 groups of 47 with the last color entry representing missing data. Each section of 47 colors will start with the color for land or ocean and end with the maximum value of white (RGB 255,255,255).
	
	The remaining colors will be evenly ramped from the starting color to the ending color (a short program saved time for this step).
	
	You can download the color table upc_t_s.tbl generated for this composite satellite image.
	
4. ** Edit imgtyp.tbl**

	Add an image type entry for this band 2\*\*(10 - 1) image for sensor 11 (**Gini ID 99 above**) into `GEMTBL/sat/imgtyp.tbl` if it does not already exist.
	
   		IRSAT-BASE           COMPOS        0     94     11   2**9      1 upc_t_s.tbl
   		
   		
5. **Draw Map**

	Display the composite image in GEMPAK programs as a satellite image and overlay data as desired.

	    MAP      = 1
	    GAREA    = dset
	    PROJ     = sat
	    SATFIL   = COMP_20070530_1200
	    LUTFIL   = upc_t_s.tbl

   


To create a realtime product, schedule the conversion of the IR image to grid and generation of the composite image.