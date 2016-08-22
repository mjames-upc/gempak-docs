---
title: PGEN_CCFP
layout: default
---


# Collaborative Convective Forecast Product (CCFP)


I. Functionality 

The CCFP is generated in two steps.  First, the CCFP is drawn by selecting
the "CONV FCST" object under the "SIGMET" class.  Second, after the object
is drawn, the CCFP text product is generated by selecting the "CCFP" object 
under the "PROD" class.  CCFP objects are either a four-sided area grouped
with a text box that lists convection attributes, or just a line.

II. CCFP Drawing 

Draw a CCFP by selecting class "SIGMET" and object "CONV FCST". 
On the "Collaborative Collective" GUI, choose either "Area or "Line".  

A. Area Regions

If area is chosen, specify "Coverage", "Tops", "Probability", "Growth", "Speed" 
and "Direction" in the "Collaborative Convection" GUI.  Define the four 
corner points of the desired region by clicking the left mouse button.  When 
you are finished drawing an area, you will be prompted to place the CCFP text 
box.  This text box is automatically grouped with the area object.  Its color
is determined by the coverage amount, 25-49% : yellow, 50-74% : orange, 
75-100% : red. 

B. Lines

If the "Line" is selected, then only an line object is drawn.  Convection 
attributes, e.g., "Coverage", are not specified, thus no text box is 
associated with the CCFP line.

III. CCFP Editing

A.  Area Regions

To edit the CCFP, set the class to "Any" or "SIGMET".  If a CCFP region is 
selected, its shape may be modified by dragging a vertex.  In addition,
the "Collaborative Convection" GUI is invoked when editing, allowing the
modification of coverage, probability, etc.  Click the "Apply" button to
update the selected CCFP object with the new attributes.  The CCFP text
box will update, accordingly.  The attributes of the text box, i.e., 
text font, text size, etc, are modified by setting the class to "Any" or
"Text" and selecting the text box object.  Note the the text content can
only be changed by setting the attributes in the "Collaborative Convection"
GUI.  The text box may also be moved using the "Mov" action.

B. Lines

To edit a line, set the class to "Any" or "SIGMET".  The line can be stretched,
shrunk, or moved by selecting either line vertex.
 
IV.  CCFP Text Production

A text file is produced from all CCFP areas and lines in a VGF.  The text
file contains information about the convection and the latitude and 
longitude of CCFP areas and lines.

When all CCFP areas have been drawn and edited, generate the CCFP text file
by selecting "PROD" and then "CCFP".  Choose the "Issue Time" and 
"Valid Time".  The choices for the issue and valid time hours are obtained
from the table, $GEMTBL/pgen/ccfp.tbl.  The hours are appended to the 
appropriate dates in the GUI using the system clock.

Click "Continue" and "Save" to save the CCFP product information to the text
file.  The text file name is "issue_time.ccfp" where "issue_time" is 
in the format "yyyymmdd_hhnn".

The contents of the CCFP text file are as follows:

Line 1 - "CCFP" followed by the issue and valid times,
Line 2 - "AREA" followed by 6 integers, then the number of points, the
         latitude and longitude point locations * 10, and finally the 
         latitude and longitude of the text box * 10.
   Integer 1 - Coverage    ( 1 - 75-100%, 2 -  50-74%, 3 - 25-49% )
   Integer 2 - Probability ( 1 -  70-100, 2 -   40-69, 3 -   1-39 )
   Integer 3 - Growth      ( 1 -    "++", 2 -     "+", 3 -   "NC", 4 - "-" )
   Integer 4 - Tops        ( 1 -    370+, 2 - 310-370, 3 -   <310 )
   Integer 5 - Speed       ( whole knots to nearest 5 )
   Integer 6 - Direction   ( whole degrees to nearest 16-pt compass )

-OR-

Line 2 - "Line" followed by the number of points and then the latitude and
         longitude point locations * 10.

Line 2 is repeated as many times as there are CCFP objects in the VGF file.

The VGF file may be saved and used as input to the GPMAP program for 
graphical product creation in a variety of output formats including GIF.