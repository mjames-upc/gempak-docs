---
title: GPMAP Overview
layout: default
---

`gpmap` draws a map for a specified graphics area.  Plots may be drawn in any GEMPAK projection and may be overlaid on images, similar as with `sfmap`, `gpmap` can display various types of graphics products including:

1.  AWIPS
2.  AFOS
3.  watches and warnings
4.  tropical or hurricane storm tracks
5.  international SIGMETs
6.  lightning
7.  `ATCF` tracks
8.  airmets
9.  non-convective sigmets
10.  severe local storm watches
11.  winter storm warning, watch and advisories
12.  convective sigmets
13.  ensemble cyclone tracks

Images are animated if more than one image file is specified in
`SATFIL` or `RADFIL`.  Images are sampled to correspond to the
geographic area specified by `GAREA`.


## GPMAP Input Parameters

<pre>
[MAP](/cgi-bin/gempak/manual/variables_index?map)       Map color/dash/width/filter flag
[MSCALE](/cgi-bin/gempak/manual/variables_index?mscale)    fgc;bgc;mask/units/lat;hide/values/anch/x;y/ln;wd/freq|text_info|t
[GAREA](/cgi-bin/gempak/manual/variables_index?garea)     Graphics area
[PROJ](/cgi-bin/gempak/manual/variables_index?proj)      Map projection/angles/margins|drop flag
[SATFIL](/cgi-bin/gempak/manual/variables_index?satfil)    Satellite image filename(s)
[RADFIL](/cgi-bin/gempak/manual/variables_index?radilf)    Radar image filename(s)
[IMCBAR](/cgi-bin/gempak/manual/variables_index?imcbar)    Color/ornt/anch/x;y/ln;wd/freq
[LATLON](/cgi-bin/gempak/manual/variables_index?latlon)    Line color/dash/width/freq/inc/label/format
[PANEL](/cgi-bin/gempak/manual/variables_index?panel)     Panel loc/color/dash/width/regn
[TITLE](/cgi-bin/gempak/manual/variables_index?title)     Title color/line/title
[TEXT](/cgi-bin/gempak/manual/variables_index?text)      Size/fnt/wdth/brdr/N-rot/just/hw flg
[CLEAR](/cgi-bin/gempak/manual/variables_index?clear)     Clear screen flag
[DEVICE](/cgi-bin/gempak/manual/variables_index?device)    Device|name|x size;y size|color type
[LUTFIL](/cgi-bin/gempak/manual/variables_index?lutfil)    Enhancement lookup table filename
[STNPLT](/cgi-bin/gempak/manual/variables_index?stnplt)    Txtc/txt attr|marker attr|stnfil#col
[VGFILE](/cgi-bin/gempak/manual/variables_index?vgfile)    Vgfile | scale file | attribute file | filter
[AFOSFL](/cgi-bin/gempak/manual/variables_index?afosfl)    AFOS Graphics File
[AWPSFL](/cgi-bin/gempak/manual/variables_index?awpsfl)    AWIPS Graphics File
[LINE](/cgi-bin/gempak/manual/variables_index?line)      Color/type/width/label/smth/fltr/scflg
[WATCH](/cgi-bin/gempak/manual/variables_index?watch)     End time|Wtch clrs|Wtch Tm;Status Ln Tm|Watch Num;
[WARN](/cgi-bin/gempak/manual/variables_index?warn)      End time|TS;TN;FF clrs|Tm|Lb|Outline|Poly
[HRCN](/cgi-bin/gempak/manual/variables_index?hrcn)      End time|colors|syms|Tm|Lb|Mt|Qw|F12|F24|F36|F48|F72|F96|F120|Name
[ISIG](/cgi-bin/gempak/manual/variables_index?isig)      End time|colors|Sym|Tm|Id|Mv|Fl
[LTNG](/cgi-bin/gempak/manual/variables_index?ltng)      End time|time ints/colors|markers
[ATCF](/cgi-bin/gempak/manual/variables_index?atcf)      Time|colors|models|Tm|Id|Mv|Mkr|Name
[AIRM](/cgi-bin/gempak/manual/variables_index?airm)      Airmet Plotting Attributes
[GAIRM](/cgi-bin/gempak/manual/variables_index?gairm)     GAirmet Plotting Attributes
[NCON](/cgi-bin/gempak/manual/variables_index?ncon)      NCON attributes
[CSIG](/cgi-bin/gempak/manual/variables_index?csig)      End time|0_Hr;1_Hr;2_Hr;OL clrs|Seq0|Tm|Mv|Fl|Insty|Seq1|Seq2
[SVRL](/cgi-bin/gempak/manual/variables_index?svrl)      End time|SVRL clrs|Tm|Lb|Outline|Clr
[BND](/cgi-bin/gempak/manual/variables_index?bnd)       Bnd name/color/fillsiz/fillpat/filt/minpts!lincol/linpat/linwid!mr
[TCMG](/cgi-bin/gempak/manual/variables_index?tcmg)      End time|colors|center
[QSCT](/cgi-bin/gempak/manual/variables_index?qsct)      QuickScat Plotting Attributes
[WSTM](/cgi-bin/gempak/manual/variables_index?wstm)      End time|WN;WT;AD clrs|Tm|Lb|Outline/WN;WT;AD lwidth
[WOU](/cgi-bin/gempak/manual/variables_index?wou)       End time|Mrkr and Otln clrs|Tm|Lb|Wt|Clr|Mrkr|Otln|Fill/Fill clrs|
[WCN](/cgi-bin/gempak/manual/variables_index?wcn)       End time|Mrkr and Otln clrs|Tm|Lb|Wt|Clr|Mrkr|Otln|Fill/Fill clrs|
[WCP](/cgi-bin/gempak/manual/variables_index?wcp)       End time|Wtch clrs|Tm|Lb|Clr
[ENCY](/cgi-bin/gempak/manual/variables_index?ency)      Time|colors|models|Tm|Prs|Mkr|Ccd;wlevs|Fcst_Hour
[FFA](/cgi-bin/gempak/manual/variables_index?ffa)       End time|FF;FA clrs|Tm|Lb|Ic|Outline/FF;FA lwidth
[WSAT](/cgi-bin/gempak/manual/variables_index?wsat)      WindSAT Plotting Attributes
[ASCT](/cgi-bin/gempak/manual/variables_index?asct)      AScat Plotting Attributes
[TRAK1](/cgi-bin/gempak/manual/variables_index?trak1)     Jason-1 Ground Track Prediction Plotting Attributes
[TRAKE](/cgi-bin/gempak/manual/variables_index?trake)     ENVISAT Ground Track Prediction Plotting Attributes
[TRAK2](/cgi-bin/gempak/manual/variables_index?trak2)     Jason-2 Ground Track Prediction Plotting Attributes
[OSCT](/cgi-bin/gempak/manual/variables_index?osct)      OScat Plotting Attributes
[SGWH](/cgi-bin/gempak/manual/variables_index?sgwh)      Significant Wave Heights Plotting Attributes
[ASDI](/cgi-bin/gempak/manual/variables_index?asdi)      End time|Mode|DepArr|time increment/clrs or ht range/clrs|time lmt
</pre>


## Exercise #6 (NIDS Display)

Display the current NIDS Base Reflectivity image overlain with county boundaries and interstates

1.  Begin by finding the latest NIDS file for KFTG (Front Range Airport, near Denver):

        ls $GEMDATA/nexrad/NIDS/FTG/N0Q/ | tail -1
        
2.  set `RADFIL` to this latest file available (full path name), set projection to use to radar file, set the graphics area to the entire set:
        
        radfil = $GEMDATA/nexrad/NIDS/FTG/N0Q/N0Q_20121030_0005
        proj   = rad
        garea  = dset
        map    = 1
        lutfil = default
        imcbar = 1

3.  After running `gpmap` to check that the reflectivity scan shows correctly, define the `$mapfil` variable to add roads and county boundaries, and define `map` to specify different colors for each map:
    
        $mapfil = hicnus.nws + hiisus.nws + hiuhus.nws + hipowo.cia
        map     = 23         + 15/1/2     + 14/1/1     + 1/1/1

    ![image](gpmap1.gif)

    ## What is this $MAPFIL Variable?

    You won't find this variable on any user interface, it is a **hidden variable**. Why? Good question.

    `$MAPFIL` defaults to a medium-resolution political boundary map of the world (countries and states), caled `HIPOWO.CIA`.  Alternate maps, such as lakes, rivers and more detailed political boundaries, can be called as well.

    The mapfiles themselves are located in the directory `$GEMMAPS`.  The higher the resolution of the map, the longer it takes to draw (best to use low-res for global maps).

    You can specify multiple map files using the `+` character to separate each file name:

        $mapfil = file1 + file2 + .... + fileN

    The map files are named by concatenating the **resolution**, **map boundaries**, and **area** with the three-letter source file type. For example, the medium-resolution political world map from GSFC is called `MEPOWO.GSF` (`ME` = medium, `PO` = political boundaries, `WO` = world).

    > ![](warning.gif width=30 align=left) GEMPAK will "remember" the last map file used. If you forgot to reset `$MAPFIL` after some customization, the GEMPAK program will use the last definition you entered (on everything).

    We will explore mapfiles again in this tutorial, but for now, while still in `gpmap`, reset the mapfile to the default:

        $mapfil = hipowo.cia


    ## Exercise #7 (Watches and Warnings)

    Using the latest visible satellite image, display
        the latest watches, warnings, international SIGMETs, lightning,
        ATCF tracks, airmets and non-convective and convective sigmets,
        SLS watches, winter storm messages, and all tropical
        disturbances.

    Be sure that `SATFIL` is defined correctly!

        MAP      = 1/7
        MSCALE   = 0
        GAREA    = us
        PROJ     = sat
        SATFIL   = $SAT/EAST-CONUS/1km/VIS/VIS_20121029_2132
        RADFIL   =  
        IMCBAR   =  
        LATLON   =  
        PANEL    = 0
        TITLE    = 1
        TEXT     = 1
        CLEAR    = y
        DEVICE   = xw
        LUTFIL   =  
        STNPLT   =  
        VGFILE   =  
        AFOSFL   =  
        AWPSFL   =  
        LINE     =  
        WATCH    = last
        WARN     = last
        HRCN     = all
        ISIG     = last
        LTNG     = last
        ATCF     = last
        AIRM     = last
        GAIRM    =  
        NCON     = last
        CSIG     = last
        SVRL     = last
        BND      =  
        TCMG     =  
        QSCT     =  
        WSTM     = last
        WOU      =  
        WCN      =  
        WCP      =  
        ENCY     =  
        FFA      =  
        WSAT     =  
        ASCT     =  
        TRAK1    =  
        TRAKE    =  
        TRAK2    =  

![image](gpmap3.gif)

1.  `WATCH` sets the ending time and the colors for plotting the watches.
2.  `WARN` sets the ending time and the colors for plotting warnings.
3.  `WSTM` sets the ending time and the colors for plotting winter storm warning, watch, and advisory.
4.  `FFA` sets the ending time and the colors for plotting flash flood and areal flood watches.
5.  `CSIG` sets the ending time and the colors for plotting convective sigmets.
6.  `HRCN` sets the ending time and the colors for plotting tropical depressions, storms, and hurricane positions. Optionally, a specific storm name may be entered to display only that specific tropical disturbance.
7.  `ISIG` sets the ending time and the colors for plotting international SIGMETs.
8.  `LTNG` sets the ending time, time increments, colors and markers for plotting lightning data.
9.  `ATCF` sets the time, models and colors for plotting `ATCF` (Automated Tropical Cyclone Forecast) tracks.  As with `HRCN`, a specific storm name may be entered.
10.  `AIRM` sets the ending time and the colors for plotting airmets.
11.  `NCON` sets the ending time and the colors for plotting non-convective sigmets.
12.  `SVRL` sets the ending time and the colors for plotting severe local storms watches.
13.  `WOU` sets the ending time and the colors for plotting the watch outline update (`WOU`).
14.  `WCN` sets the ending time and the colors for plotting the watch county notification(`WCN`).
15.  `WCP` sets the ending time and the colors for plotting the watch corner product.
16.  `ENCY` sets the initial time, colors, model names, and date/time, pressure and marker flags for plotting of the ensemble cyclone tracks.
