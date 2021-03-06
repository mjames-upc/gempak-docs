---
title: SIGBUFR
layout: default
---



SIGBUFR converts all the High Level (SWH) and Mid Level (SWM) 
Significant Weather BUFR files for a specified date/time and 
forecast hour to at most two ASCII output files using the UKMET 
browsable dataset format.

# Usage

    sigbufr    YYMMDD/HHNN FF hi_outfile.name+mid_outfile.name

    YYMMDD/HHNN    GEMPAK date/time
    FF             Valid forecast hour (must be 18 or 24)
    outfile.name   Output file names (optional)

# Program Description

SIGBUFR reads a series of high and/or mid level significant weather
files in BUFR format for a single date/time and forecast hour, and
writes out either one or two ASCII files using the UKMET browsable 
dataset format (see "Representing WAFS Significant Weather (SIGWX)
Data in BUFR", version 2.3, November 2004, for documentation).  The
BUFR files use the following naming convention, with WMO headers 
and the date/time and forecast hour defining the file name:

For high level,

    JUWf96.YYYYMMDDHH - JETS (Jetstreams)
    JUCf00.YYYYMMDDHH - CAT (Clear air turbulence)
    JUBf99.YYYYMMDDHH - CLOUD (Cumulonimbus)
    JUTf97.YYYYMMDDHH - TROP (Tropopause)
    JUFf00.YYYYMMDDHH - FRONTS (Frontal Systems)
    JUVf00.YYYYMMDDHH - V_T_S (Volcanoes, Storms, Radiation)

and for mid level,    

    JUTf00.YYYYMMDDHH - JETS (Jetstreams)
    JUMf00.YYYYMMDDHH - CAT (Clear air turbulence)
    JUNf00.YYYYMMDDHH - CLOUD (Cumulonimbus)
    JUOf00.YYYYMMDDHH - TROP (Tropopause)
    JUJf00.YYYYMMDDHH - FRONTS (Frontal Systems)
    JUVf00.YYYYMMDDHH - V_T_S (Volcanoes, Storms, Radiation)

where

    f - the valid forecast hour, D for 18 and E for 24


(Note that the V_T_S BUFR file contains data common to both high and
mid level charts.)

If either output filename is not specified on the command line, then
the default name `SIGWXHI.txt` will be used for the high level file 
and `SIGWXMID.txt` for the mid level file.  A single output file 
name with no `+` is assumed to be a high level file name.  Default 
files will be created locally. 

The date/time and forecast hour input are used to construct the 
input BUFR file names.  The alias `SIGBUFff` is used to create the 
file name template, `JU*D*.YYYYMMDDHH` or `JU*E*.YYYYMMDDHH`, from the 
`datatyp.tbl` file.  The alias, `SIGBUFff`, also sets a value for the 
path to the BUFR files.  This path is defined by the environment 
variable `$SIGWX`.  This environment variable must be set by the site 
administrator.  The template ff is the 18 or 24 valid forecast hour.


# Error Messages
    
    [SIGBUFR   6]  Feature count is !AS
    [SIGBUFR   5]  Returned value for feature is !AS
    [SIGBUFR   4]  Found feature !AS
    [SIGBUFR   3]  Time code is !AS
    [SIGBUFR   2]  Center id is !AS
    [SIGBUFR   1]  BUFR_File is !AS
    [SIGBUFR  -1]  GEMPAK date/time and valid hour must be on command line.
    [SIGBUFR  -2]  No BUFR files found for !AS
    [SIGBUFR  -3]  Valid hour must be 18 or 24, not !AS
    [SIGBUFR  -4]  Could not initialize BUFR info structure.
    [SIGBUFR  -5]  Error in BUFR_Init for file !AS
    [SIGBUFR  -6]  Error in BUFR_Get_Value for file !AS
    [SIGBUFR  -7]  Error in chart levels !AS
    [SIGBUFR -10]  End of dataset.
    [SIGBUFR -11]  File !AS not found.
    [SIGBUFR -12]  Error getting decoded value.
    [SIGBUFR -13]  End of file.
    [SIGBUFR -14]  Unknown value !AS returned by BUFR_Get_Value().
    [SIGBUFR -15]  End of message.
    [SIGBUFR -16]  File !AS is not a BUFR file.

