---
title: PGEN_SMEAR
layout: default
---

			Smear Action


I.  Functionality

The smear action is used to create a new "smeared" element by combining
one or more selected "snapshot" elements.  The smear action only works on
closed lines, AIRMETs (class MET), non-convective SIGMETs (class MET), and
GFA elements.  A small GUI window allows the user to control the color of
the smeared element.

II. Operation 

After clicking on the Smear button, the smear GUI pops up.  Click on a 
suitable element (closed lines, AIRMETs, non-convective SIGMETs, or GFA 
only) using the left mouse button.   Filled, white circles are placed on 
the points of the element to indicate the selection.  The user then confirms 
this element selection with a second mouse click (left mouse button).  Red 
squares indicate the element selection is confirmed.  A middle mouse button 
instead of the confirming click will de-select the element.

Select one or more elements.  All subsequent elements must be of the same
class, type, and area (if appropriate) as the first selected element.  That
is, if the first selected element is a GFA of type TURB, only other GFA/TURB 
elements can be selected.

Once all the desired snapshot elements have been selected, click on the
Smear button on the Smear GUI.  The new, smeared element will be created.  It 
will include a union of the areas of all selected figures and the worst-case 
flight levels (highest top, lowest bottom) of all the snapshots.


III.  Rules

For GFA elements the smeared figure will be given the worst case description.
Worst case is defined as the description furthest toward the bottom of the
description list.  This list is taken from the gfa.tbl table and is assumed
to be ordered by severity.

For AIRMETs, SIGMETs, and GFA elements, the text is placed in the same
relative location from the element's center as the text placement of the 
first selected element.

