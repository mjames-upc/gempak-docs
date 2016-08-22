---
title: Introduction
layout: default
---

# What is GEMPAK?

[GEMPAK](http://www.unidata.ucar.edu/software/gempak/) (the **GE**neral **M**eteorology **PA**c**K**age, also called NAWIPS) is a suite of programs, libraries, graphics routines, and device drivers for the analysis, display and diagnosis of geo-referenced data. GEMPAK was orginially developed by the Severe Storms Laboratory at [NASA's Goddard Space Flight Center](www.nasa.gov/centers/goddard/home) in the 1980s, and was used operationally at NCEP National Centers up until the migration to AWIPS II. The Unidata GEMPAK release incorporates several additions developed at UCAR to enhance the use of data acquired through the IDD, as well as with instructional case studies.

# Workshop Specific Instructions

This User Guide was originally written for the Unidata GEMPAK Training Workshop, and assumes that the user has available a Linux (or equivalent) terminal window (csh or bash) to run GEMPAK programs. First time users are encouraged to thouroughly read the [GEMPAK installation instructions]().   GEMPAK requires C and Fortran compilers and Open Motif libraries be installed to work properly.   

In a workshop environment, GEMPAK programs are run as user `gempak`, making `/home/gempak/` the use home directory, and `/home/gempak/NAWIPS` the root GEMPAK program directory.  Users should consult the GEMPAK Installation instructions to be certain that the appropriate environmental variable file (`/home/gempak/NAWIPS/Gemenviron` or `/home/gempak/NAWIPS/Gemenviron.profile`) is sourced in your `.cshrc` or `.bashrc` file, respectively.  

>## tcsh/csh

Inspect the file with  `vi`, `cat`, or `more`:

    vi .cshrc

and be certain that this line exists and is valid

    source /home/gempak/NAWIPS/Gemenviron

>## bash

    vi .bashrc

ensure that this line exists and is valid

    . /home/gempak/NAWIPS/Gemenviron.profile

Save the file, close the terminal window and launch another one to confirm that GEMPAK environmental variables are available to your session:

    env | grep GEM
    
and you should see

    NAWIPS=/home/gempak/GEMPAK7
    GEM_COMPTYPE=gfortran
    GEMPAK=/home/gempak/GEMPAK7/gempak
    GEMPAKHOME=/home/gempak/GEMPAK7/gempak
    CONFIGDIR=/home/gempak/GEMPAK7/config
    OS_ROOT=/home/gempak/GEMPAK7/os/linux64
    OS_BIN=/home/gempak/GEMPAK7/os/linux64/bin
    OS_INC=/home/gempak/GEMPAK7/os/linux64/include
    OS_LIB=/home/gempak/GEMPAK7/os/linux64/lib
    GEMLIB=/home/gempak/GEMPAK7/os/linux64/lib
    GEMEXE=/home/gempak/GEMPAK7/os/linux64/bin
    GEMPDF=/home/gempak/GEMPAK7/gempak/pdf
    GEMTBL=/home/gempak/GEMPAK7/gempak/tables
    GEMERR=/home/gempak/GEMPAK7/gempak/error
    GEMHLP=/home/gempak/GEMPAK7/gempak/help


---

# User Interface


The GEMPAK user interface is text-based, case-insensitive, and handles many abbreviations and aliases.  GEMPAK programs run as a command prompt and receive input either directly from the user or from a shell script.

The GEMPAK interface is organized by rows, with variables (`SFFILE`) first, then a short description (`Surface data file`), then the current settings (`$GEMPAK/data/hrcbob.sfc`):

    vars      description                       current setting
    ----      -----------                       ---------------
    SFFILE    Surface data file                 $GEMPAK/data/hrcbob.sfc
    AREA      Data area                         WV
    DATTIM    Date/time                         LAST
    SFPARM    Surface parameter list            SKYC;TMPF;WSYM;PMSL;;DWPF
    OUTPUT    Output device/filename            T
    IDNTYP    STNM or STID                      STID

GEMPAK programs are started simply by typing their name in your terminal window:

    sflist
    
New values are assigned by entering the definitions directly:

    sffile = $GEMDATA/nmcbob.sfc 
    area = den
    sfparm = tmpf;dwpf
    

> **List** variables with `l`

    l
    

> **Display** variable info with `d`

    d
    
> **Run** programs with `r` 

    r
    

> **Exit** programs with `e`

    e
    


## Introductory Exercise

>To begin using the GEMPAK interface, start a programs such as `sflist`:
>
>A list of all current values is followed by with a prompt on the last line.  Type `l` to show the current definitions:

    l
    
    SFFILE   = $GEMPAK/data/hrcbob.sfc
    AREA     = WV
    DATTIM   = LAST
    SFPARM   = SKYC;TMPF;WSYM;PMSL;;DWPF;BRBK
    OUTPUT   = T
    IDNTYP   = STID
    
>Run the program with `r`

    r

    PARM = SKYC;TMPF;WSYM;PMSL;DWPF;BRBK                                            

    STN    YYMMDD/HHMM      SKYC     TMPF     WSYM     PMSL     DWPF     BRBK
    BKW    910820/0600      8.00    60.00    61.00  1011.00    59.00  4190.00
    BLF    910820/0600      8.00    57.00    61.00  1010.60    56.00  4180.00
    CRW    910820/0600      8.00    63.00    10.00  1011.20    62.00  3200.00
    ...
    Parameters requested: SFFILE,AREA,DATTIM,SFPARM,OUTPUT,IDNTYP.
    
>The parameters defined by `SFPARM` are displayed for `DATTIM = LAST` (0600 UTC) and stations which fall inside the area defined by `AREA` (in this case, an area centered around West Virginia).
>
>After checking that the definition for `SFFILE` has observations to display, exit the program with the command `e`:

    e
    
---

# Help Pages

Type `phelp` in GEMPAK to view man pages for any **program** or **parameter** 

     phelp idntyp
     
     
     IDNTYP

     IDNTYP sets character or numeric station identifiers to be used for
     input or output.  The valid values are STID and STNM.  STID specifies
     station character identifiers; STNM specifies station numbers.

     If the value in IDNTYP is not STNM, the default of STID will be used.

     For example, to update station headers in SFSTNS:

       IDNTYP =        STID -- compares character ids in file with those
                               in the station table
       IDNTYP =        STNM -- compares numeric ids in file with those
                               in the station table
    
---

# Default Files

Back in the terminal window, list the files in the current working directory with `ls -la` and make note of two new files:

1.  `gemglb.nts` stores values for all GEMPAK program variables, updated by the last program run, available by default to any GEMPAK program run next.  A definition of `SFFILE` in `sflist` will be available in any other program which uses `SFFILE` (such as `sfmap`), as long as this file is available.
2.  `last.nts` stores values from the last program run, used the same as `gemglb.nts` but for the last program run.

The default values for parameters such as `SFFILE` and `SFPARM` come from default files located in `$GEMPAK/defaults/*.nts` for each program.

---

# Environmental Variables

Environment variables are used by GEMPAK to find needed executable, table, parameter, error, help, and map files without requiring user input.

    $NAWIPS - Top of the NAWIPS distribution
    $GEMPAK - Directory for the top of the GEMPAK tree
    $GEMDATA - Location of data files
    $OS_LIB - Library directory (used for installation)
    $OS_BIN - Location of executable code
    $GEMPDF - Location of parameter definition files
    $GEMTBL - Location of tables
    $GEMERR - Location of error messages
    $GEMHLP - Location of on-line help files
    $GEMMAPS - Location of map files
    

Each of these is defined in a variable definition file (`~/NAWIPS/Gemenviron` for **csh/tcsh**, `~/NAWIPS/Gemenviron.profile` for **bash**).  Depending on your shell, one of these files **MUST** be sourced in the current shell environment for GEMPAK programs to work.

1.  For **csh/tcsh**, in a terminal, type `source ~/NAWIPS/Gemenviron`
2.  For **bash**, type `. ~/NAWIPS/Gemenviron.profile`

If you're currently taking part in the Unidata GEMPAK Workshop, the above step has been taken care of for you by adding the `source` command to your `.tcsh` file, executed at login.

Check that the GEMPAK environmental variable are correct with the command:

    env| grep GEMPAK