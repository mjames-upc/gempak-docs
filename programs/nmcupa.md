---
title: NMCUPA
layout: default
---

NMCSND decodes upper-air data in NMC archive format and
writes it to a GEMPAK sounding data file.
                                                                            
                                                                            
# Input Parameters                                                                
	                                                                            
	SNEFIL    *NMC file
	SNFILE    *Sounding data file
	AREA      *Data area
	TIMSTN    *Times/additional stations
	                                                                            
	                                                                            
# Program Description                                                             
                                                                            
NMCSND decodes snounding observations in NMC Office
Note 29/124 format and writes it to the GEMPAK snounding
file given by SNFILE.  AREA is entered as the
southwestern and northeastern corner points of the
region over which stations will be included.

The NMC raw data file name is entered by specifying SNEFIL.
The file may contain either EBCIDC or ASCII data.

NMCSND will create an GEMPAK snounding file if SNFILE
does not already exist using TIMSTN to set the number
of times and stations to included in the file.
                                                                            
                                                                            
                                                                            
# Example

Load data from NMC file `nmc.snd`:
                                                                            
    SNEFIL  =  nmc.snd
    SNFILE  =  gempak.snd
    AREA    =  30;-120;55;-70
    TIMSTN  =  24/1200
                                                                            
                                                                            
                                                                            
# Error Messages                                                                  
                                                                                
	[NMC  -1]     Fatal error initializing TAE.                               
	[NMC  -2]     Fatal error reading TAE parameters.                         
	[NMC  -3]     Error opening station file !AS .
	[NMC  -4]     ... is a merged file.
	[NMC  -5]     ... is not an upper air station.
	[NMC  -6]     AREA is invalid; see help on GAREA.
	[NMC  -7]     Error in NMCTMST.
	[NMC  -8]     Error adding time ... .
	[NMC  -9]     Wrong number of parms -- check packing file.
	[NMC -10]     Unexpected data in the INPUT file.
	[NMC -11]     Neither entry in TIMSTN can be zero.
