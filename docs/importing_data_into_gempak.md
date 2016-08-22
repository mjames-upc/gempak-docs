---
title: Importing Data
layout: default
---

`sfedit` and `snedit` can be used to import non-standard data sets into GEMPAK surface and sounding file format, respectively.  These programs can also be used to modify data in existing GEMPAK files. 

- `sfedit` requires a surface data file already exists
- `snedit` will create a file if one does not already exist
- To import research data sets with stations that aren't present in the standard GEMPAK station tables, you will have to create your own station tables.
- The program `sfcfil` will created an `SF` surface data file which can then be used by `sfedit`. 
- The program `sncfil` will created an `SN` sounding data file which can then be used by `snedit`. 

## Import Raw Surface Data

To import data sets which contain PAM, MESONET, Aircraft, Dropsonde, or other special station locations, you should first create a station table.

When you create your new GEMPAK file, the program asks for the name of a station file. For research datasets, it is probable that special sensor locations will not be in any of the distributed tables. When creating your own station tables follow the format used in provided station tables.


## Exercise #14 (Import Surface Data)

[Here is a sample](http://www.unidata.ucar.edu/software/gempak/tutorial/data/astex_1.raw) of aircraft data collected during a field experiment:

    DATE        LAT    LON      PRES     HGHT     TMPC     DWPC     SSTC     SPED     DRCT
    21.9361   37.04 -25.20    975.58   433.78    14.37    11.54    17.49     5.62    78.27
    21.9389   37.05 -25.20    965.67   520.66    13.58    11.08    17.48     4.45    83.18
    21.9417   37.06 -25.20    956.32   601.89    13.22     9.09    17.49     4.18    88.79
    21.9444   37.06 -25.21    948.71    21.58    12.70     8.32    17.51     3.82    81.65
    21.9472   37.07 -25.21    942.53    21.58    12.36     7.60    17.37     4.56    85.96
    21.9500   37.08 -25.21    937.86   189.88    12.19     6.20    17.31     4.41    82.84
    21.9528   37.09 -25.22    932.87   814.19    12.40     4.69    17.17     4.44    82.12
    21.9556   37.10 -25.22    927.48   863.54    12.17     4.92    17.20     4.20    73.18
    21.9583   37.11 -25.22    919.45   934.24    11.74     4.94    17.26     3.83    61.57
    21.9611   37.12 -25.23    911.19  1010.74    11.26     5.16    17.17     3.85    58.72
    

    We would like to represent this data as a GEMPAK surface file so thatwe can plot the flight track and sea surface temperature along the path of the aircraft as individual surface station reports.

1.  Generate a surface station table and surface data file from the aircraft data. You will need to convert your raw data into the appropriate format to be read by GEMPAK (see the included data file below):
      Here are the [Station Table](http://www.unidata.ucar.edu/software/gempak/tutorial/data/astex_1.tbl) and [Data file](http://www.unidata.ucar.edu/software/gempak/tutorial/data/astex_1.dat) I created.
2.  Using `sfcfil`, create an empty GEMPAK surface file:

    
         sfoutf = test_data.sfc
         sfprmf = HOUR;PRES;HGHT;TMPC;DWPC;SSTC;SPED;DRCT
         stnfil = astex_1.tbl
         SHIPFL = no
         TIMSTN =     
         SFFSRC = text
         
    The output will be
    
         SFCFIL PARAMETERS:     
         
         New surface file:      data.sfc     
         Parameter file:        HOUR;PRES;HGHT;TMPC;DWPC;SSTC;SPED;DRCT     
         Station file:     
         
         Number of stations in STNFIL:    1412
         Number of additional stations:      0
         Total number of stations:        1412
         Total number of times:              1
         
         This file will be a standard surface file.
         Enter <cr> to accept parameters or type EXIT:
         
         The file has been created.
        
     This creates the file `test_data.sfc` in the current working directory.
    > ![](warning.gif) Be sure that `SFPRMF` is defined exactly how parameters are listed in your surface station file!
3.  Using `SFEDIT`, import the data file into the newly created GEMPAK surface file:
     > sfedit
     sfefil   = astex_1.dat
     sffile   = test_data.sfc
     GEMPAK-SFEDIT>r
      SFEDIT PARAMETERS:      Edit file:           astex_1.dat      Output surface file: test_data.sfc      Parameters to be added to file:
      HOUR PRES HGHT TMPC DWPC SSTC SPED DRCT
     Enter <cr> to accept parameters or type EXIT:

 Check your `test_data.sfc` file in the present working directory, it should be much larger in size!

 You can compare `test_data.sfc` file with a [pre-generated GEMPAK file](http://www.unidata.ucar.edu/software/gempak/tutorial/data/astex_1.gem) from the above data.

 Want to see if it worked? Try plotting the data using `SFMAP`.

 You will need to define `AREA` and `GAREA` for the dataset (look at the lat/lon in the raw file to get an idea of an approximate area). You may also want to limit `SFPARM` to only one or two parameters to begin