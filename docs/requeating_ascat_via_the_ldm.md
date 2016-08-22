## Requeating ASCAT via the LDM 

The <a href="http://www.unidata.ucar.edu/projects/index.html#idd" target="_blank">IDD</a> data feedtype <b>HRS</b> contains scatterometer winds from the METOP ASCAT sensor, which has a sensor resolution of 25 km.

METOP is polar orbiting satellite providing about two flyovers per day, more in the high latitude regions.  METOP has taken over the mid morning polar orbit previously occupied by a NOAA TIROS N satellite.

Each orbit has a duration of approximately 101 minutes. The raw data are processed by NESDIS into point values of wind speed and direction, then encoded into BUFR.

The WMO headers (`T1T2A1A2II CCCC`) for these products will be of the form:

     T1:     J for ASCAT
     T2:     S
     A1:     X 
     A2:     X
     II:     Region (see table below)
     CCCC:   KNES
     
Therefore an LDM pattern action for these ASCAT bufr files will be:

	# ASCAT BUFR
	HRS     ^JSXX(..) KNES ([0-3][0-9])([0-2][0-9])([0-6][0-9])
        FILE    data/gempak/ascat/(\2:yyyy)(\2:mm)\2\3.ascat
        
Parenthesis in a pattern actuion regular expression allow for character in the WMO head, such as origin station and date and time, to be used for the <i>writing</i> of the data file.  In the above example, the ASCAT bufr files are written to `$GEMDATA/ascat/` with filename convention `YYYYMMDDhh.ascat`, so for 1500 UTC August 6 2013, the file would be named `2013080615.ascat`.

The ASCAT scatterometer wind products will be provided over the following nine geographical regions which have an aggregate area of coverage from 75N to 35S and from 35W to 130E (crossing the international dateline): 


## GEMPAK Table Configuration

The table responsible for organizing GEMPAK data file access is `$GEMTBL/config/datatype.tbl`, where `$GEMTBL` is an environmental variable which points to the GEMPAK table directory, typically `/home/gempak/NAWIPS/gempak/tables/`). 

With GEMPAK installed, view the file with the command:

	vi /home/gempak/NAWIPS/gempak/tables/conig/datatype.tbl
	
Once open, search for the `ASCT` entry with the <b>vi</b> command `/ASCT`, or from the shell with the command `grep ASCT datatype.tbl`:

	> cd $GEMTBL/config/
	> grep ASCT datatype.tbl
	ASCT         $GEMDATA/ascat           YYYYMMDDHH.ascat                               CAT_MSC  SCAT_NIL   -1   1440     60      OFF/0/0      4

The first three entries in the above line organize the data as follows:

	Alias: ASCT
	Data Directory: $GEMDATA/ascat
	File Template: YYYYMMDDHH.ascat

The other definitions for this entry should be defined as such:

	Category: CAT_MSC
	Sub-category: SCAT_NIL
	# of Frames: -1
	Range: 1440
	Interval: 60
	Bin by # Hours: OFF/0/0
	Time match: 4
	
The above entry in `datatype.tbl` will allow you to load ASCAT scatterometer data files with the GUI program `nmap2`.

## Displaying ASCAT winds in NMAP2

ASCAT winds are loaded with the 

## Displaying ASCAT winds in GPMAP

The GEMPAK program <b>GPMAP</b> will display ASCAT bufr files using the <b>QSCT</b> parameter.

### Example

Use datatype `ASCT` and provide the wind speed ranges, colors and display flags as defined in the `QSCT` parameter definition:

	QSCT = asct|last|6;12;18;24;30;36;42;48;54;60|30;6;26;24;21;23;5;17;8;14|31;31;31;31;31;31;31;31;31;31|.2;.4;1;5|0|1|1|Y|Y|Y|Y|Y
	
	MAP      = 1
	GAREA    = -18;-55;30;10
	PROJ     = MER
	SATFIL   =  
	RADFIL   =  
	IMCBAR   =  
	LATLON   =  
	PANEL    = 0
	TITLE    = 1
	TEXT     = 1
	CLEAR    = YES
	DEVICE   = XW
	LUTFIL   =  
	STNPLT   =  
	VGFILE   =  
	AFOSFL   =  
	AWPSFL   =  
	LINE     = 3
	WATCH    =  
	WARN     =  
	HRCN     =  
	ISIG     =  
	LTNG     =  
	ATCF     =  
	AIRM     =  
	GAIRM    =  
	NCON     =  
	CSIG     =  
	SVRL     =  
	BND      =  
	TCMG     =  
	QSCT     = asct|last|6;12;18;24;30;36;42;48;54;60|30;6;26;24;21;23;5;17;8;14|31;31;31;31;31;31;31;31;31;31|.2;.4;1;5|0|1|1|Y|Y|Y|Y|Y

When run, the X-Window map should look like

<img src="http://www.unidata.ucar.edu/staff/mjames/gempak/asct.gif">

Not very exciting, but it confirms that the data are plotted correctly.

## More on the GPMAP QSCT variable

* <i>Note that the following document refers to the now-defunct <b>QuikScat</b> but that the <b>QSCT</b> variable is used to display bufr data from any scatterometer satellite.</i>

**QSCT** is the ending valid time for the QuikScat or ambiguity wind data,
the speed intervals and colors, the wind barb size and width and
plotting flags.  Skip is a value that indicates how many rows and data
points to skip when plotting.  The flags include High Wind Speed, Low
Wind Speed, Rain, Sensor Availability.
	
	 Data type | End time | Speed intervals | colors1 | colors2 |
	 Arrow/Barb shaft size;Arrow/Barb width;Arrow head size;
	 Type of wind vector | Skip | Time stamp interval | Time stamp color |
	 Line Width | High Spd | Low Spd | Rain | Availability | Rain Colors |
	 Plot Circles

The data type is a selection to plot **QSCT**, **QSCT_HI**, **AMBG1**, **AMBG2**, **AMBG3**, or **AMBG4** data.

The ending time is the latest time for which QuikScat data or QuikScat
ambiguity data will be plotted.  The ending time is given as a GEMPAK
date/time string.  Any missing items from the string will be filled in
by the system time.  The ending time may also be LAST.  LAST will use
the system time and plot all QuikScat data for the preceding 4 hours.
ALL is not accepted as an ending time for QuikScat data.

The speed intervals and colors may each be specified using either a list
separated by semicolons or a range in the form first-last-increment.
Speed intervals are given in knots.  If any color is missing, a default
will be used.  If no interval and color are given, a single speed
interval of 200 knots will be used.  This means that any wind speed less
than 200 knots will be plotted.  The default color for the single speed
is green.  If the rain flag in the data is true, and the rain colors flag
is true, the wind bard is plotted in the second colors for that wind speed.
If the rain flag is false or the rain colors flag is false, then the
first color is used.

The wind arrow/barb attributes are the shaft size of the arrow or barb,
width of the arrow or barb, size of the arrow head, and the type of wind
vector separated by a semicolon.  The default shaft size is 0.2, the
default width is 1, the default arrow head size is .4 , and the default
type of wind vector is 5 for wind barb.  The other values for type of wind
vector is 1 or 3 for directional arrow and 4 for regular arrow.  If no
value is given for the type of wind vector, then if the arrow head size is
greater than 0, directional arrows will be plotted, otherwise wind barbs
will be plotted.

The Skip value is an integer used for skipping rows and columns of data
when plotting the winds.

The time stamp interval is the time interval in minutes. Line width is
the width of the time stamp. The default value is 30 time stamp interval
and 1 for line width.

The flags correspond to flags in the QuikScat data.  The High Speed,
Low Speed, Rain present and Sensor Availability flags allow the user
to display wind data that has any of these attributes.  The default
for all flags is NO.

The Plot Circles flag indicates whether circles should be plotted along
with the wind barbs/arrows for rain flagged winds.