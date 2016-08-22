---
title: DATETIME
layout: default
---

    datetime [option] input_time [[hours[:minutes]] [output_format]]
    
    Options:
    -s      Subtract the hours and minutes
    -h      Display this help message
    
* input_time    is a date/time in the form YYMMDD/HHNN.

* hours:minutes is optional and defines the amount of time
        to add or subtract from the input time.

* output_format is an optional string defining the format
        of the output date/time string. The valid
        formats are defined in the Unix man page for 
        the 'date' command.
            (The default format is "%y%m%d/%H%M")

If the input time is not correct, this message is displayed and the
program exits with a non-zero status value. If the program runs to
completion, the status value is set to zero.

