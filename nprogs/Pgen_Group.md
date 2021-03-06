---
title: PGEN_GROUP
layout: default
---

# Group Action 


I.   Functionality

The group action puts objects into pre-defined logical groups.  Grouping
allows actions to be performed on a set of objects, for example, a group of 
objects can be moved.  Grouping also allows assigning meteorological "value"
to a set of objects, for example assigning an arrow line, hash mark, and a wind 
barb to the JET group.  Grouped objects are used by various product generation
functions to generate products. For example, outlook text products are 
created using grouped line and text objects. 

The group action allows objects to be grouped as they are drawn, or objects can
be assigned a group after they are drawn.

Valid groups supported by product generation are:

	CLOUD     TURB      FRONT     JETS      HIGH      LOW 
	OUTLOOK   LABEL     TROPICL   STNMDL    MRFSTN    HAILOTLK 
	TORNOTLK  WINDOTLK  TOTL_SVR  FIREOUTL  CATG_SVR  MESO_DSC
        TSTMOLK

NMAP/NMAP2 accesses the group names by reading the table 
$GEMTBL/pgen/grptyp.tbl.  Note that new group names cannot be added to the 
grptyp.tbl but must be coordinated with the Computing Development Branch.

II.  Operation

Click on the "Group" button to either create a new group or add objects to an 
existing group.  In either case, clicking on the "Group" button puts
product generation into group mode.  The "VG Group Selection" pop-up is
invoked and remains visible until the group mode is terminated.

To create a group, click the "Group" button.  The "VG Group Selection"
popup is invoked.  Select the desired group type, e.g., "Jets" from 
this GUI.  Draw the desired objects as is normally done by selecting
them from the product generation palette and placing them.  As objects are 
drawn they are put into the group listed in the "VG Group Selection" GUI.   
A yellow box surrounding the grouped objects with yellow triangles for each 
object vertex indicates which objects are being grouped.  The left mouse
button toggles whether a selected object is in/not in a group when not 
drawing an object.  In this way, existing objects can also be added to the 
group by clicking on them.  Click the middle mouse button to end the current
group.  A new group type can then be selected for other objects or the
middle mouse button is clicked again to exit the group mode.

To add to a group click the "Group" button.  Select an object in the 
pre-existing group.  The group type in the "VG Group Selection" GUI will
list the group name for the selected object.  Add to the group by selecting
the desired objects from the product generation palette and drawing or placing 
them.  The left mouse button toggles whether a selected object is in/not in a 
group as described above.  Click the middle mouse button to end the selected
group.  A new group can then be selected or click the middle mouse button 
again to exit the group mode.

Multi-select is the default select type while in the group mode.  Multiple 
objects can be selected for grouping by pressing the left mouse button and 
dragging a box around the desired objects.

III. Rules 

A.  Objects Which Cannot Be Grouped 

    The Track, Sigmet, Watch and CCFP objects cannot be grouped.

B.  Object Attribute Editing

    Object attributes e.g., color, cannot be edited when an object is
    selected while in group mode.

C.  Line Labeling Interactions

    The line, front, and symbol labeling option in the "Line Attributes",
    "Front Attributes", and "Symbol Attributes" GUIs is available while in the 
    group mode.  However, the group type is set and controlled by the "Group" 
    action.  To change the group type in the attributes GUI, the user must 
    select it in the "VG Group Selection" GUI, if the "Group" action is invoked 
    while labeling.

D.  Group Type Assignment Upon Activation of the "GROUP" Action

    The first time the "GROUP" action is invoked, the group type is the first 
    group name that appears in the table, $GEMTBL/pgen/grptyp.tbl.  Subsequent 
    activations of the "GROUP" action use the most recent group type set by 
    the GUI.  If product layering is invoked, then the "Group" action uses
    the most recent group type set for the active layer. 

    Note that the group type set by the "GROUP" action is independent of the 
    group type set by the attribute GUIs.  For example, if the group is set 
    to OUTLOOK by using the label feature in the "Line Attributes" GUI, 
    OUTLOOK is not set for the "GROUP" action.  Also note that the attribute
    GUIs use the group type specified for each object type in the table,
    $GEMTBL/pgen/setting.tbl as the default value.  If the group type is 
    changed for an object type using the attribute GUI, it is remembered
    for the object type the next time the attribute GUI is invoked. 

E.  Group Assignment While "GROUP" is Active

    The first group type found when selecting objects is used as the 
    group type for all subsequent objects while in the group mode.  
    If an object of a different group type is selected, its group type
    will be changed to the type set for the group mode.

