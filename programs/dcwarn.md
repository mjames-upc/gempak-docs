---
title: DCWARN
layout: default
---


DCWARN decodes flash flood, tornado and severe thunderstorm warning 
reports from a real-time data feed, or from a file fed to the program 
through standard input, and writes the data to an ASCII file. 
The program is controlled by inputs to the command line.

The inputs are program options and the output file name or template.
For example, for real-time data feeds:

	dcwarn [options] output_file

If running the program interactively with standard input, the `-c`
option must be used.  The input file must also be specified.
For example:

	dcwarn -c YYMMDD/HHNN [other_options] output_file < input_file

A template may be used to specify the output file name.  The file
name template uses the date and time of the bulletin or report
to replace the following characters.

	YYYY or YY	Year with or without the century
	MM		Month number
	DD		Day
	HH		Hour
	NN		Minute


 The format of the output ASCII file is as follows:

    |Type|Start_time|End_time|Orig_station|Corr_flag|Etn
	lat lon lat lon lat lon ...
    County_station_table_information_1
    County_station_table_information_2
	...
    County_station_table_information_N

 Where: 
 
 * `Type` is SVR (thunderstorm), TOR (tornado) or FFW (flash flood)
 * `Start_time` and `End_time` are full GEMPAK date/time strings
 * `Orig_station` is the WFO that issued the warning
 * `Corr_flag` is a flag indicating a correction/test.  
 
    Prior to release 5.11.3:
    
	* 0	Not a correction; not a test
    * 1	A correction; not a test
	* 2	Not a correction; a test
	* 3	A correction; a test
    
    From release 5.11.3, the above is still valid, but if
    there is a correction letter, then the value would be
    greater than 3:
        If it is a test, then the `Corr_flag` is greater
    than or equal to 256.  So subtract 256 to get the integer
    equivalent of the ASCII code of the correction letter.  If
    it is greater than 3, but less than 256, then `Corr_flag` is
    the equivalent of the ASCII code of the correction letter.
 * `Etn` is the Event Tracking Number

 Extra spaces may appear anywhere in this line of information,
 except in the first character position. The first character must
 be a bar (|).

 The lat lon pairs represent the warning polygon.  They are in degrees
 multiplied by one hundred.

 The County_station_table_information is read using the FORTRAN format
 (A8,1X,I6,1X,A32,1X,A2,1X,A2,1X,F9.2,1X,F9.2,1X,F9.2,1X,I2,1X,A20).
 The county information is the same as in the GEMPAK station tables.

