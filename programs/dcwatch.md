---
title: DCWATCH
layout: default
---

DCWATCH decodes WWUS40 format Severe Thunderstorm and Tornado watch
box bulletins from a real-time data feed, or from a file fed to the 
program through standard input, and writes the data to a GEMPAK ship
format file.  The program is controlled by inputs to the command line.

The inputs are program options, and the output file name or template.
For example, for real-time data feeds:

	dcwatch [options] output_file

If running the program interactively with standard input, the `-c`
option must be used.  The input file must be also be specified.
For example:
		
	dcwatch -c YYMMDD/HHNN [options] output_file < input_file

A template may be used to specify the output file name.  The file
name template uses the date and time of the bulletin or report
to replace the following characters.

	YY		Year without the century
	MM		Month number
	DD		Day
	HH		Hour
	NN		Minute

	User Controled parameters	Suggested Default:
	-------------------------	-----------------
	Parameter file			watch.pack
	Station table   		sfworld.tbl
	Maxtim				1500
