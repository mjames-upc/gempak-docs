---
title: PGEN_CHANGEGROUP
layout: default
---

# Change Group Action


I.  Functionality

The Change Group action allows the user to change all groups of one type to
another type.  For example this action can be used to change all groups of 
type OUTLOOK to type HAILOTLK without ungrouping and regrouping manually. 


II.  Operation

Draw several vg elements and group some of them together in a number of 
different groups.  Click on the Change Group action.  The VG Group Change
window will pop up.  The Current Group menu will contain all the group types
that are currently in use in the work file.  The Change To menu will contain
all the group types defined in the $GEMTBL/pgen/grptyp.tbl.  Select the 
combination of current group and change to group desired then click on the
Apply button.  All the groups of the type selected in the Current Group menu
will be changed to the type defined in the Change To menu, while maintaining
group integrity.

The first entry in the Current Group menu is "All Groups".  When this is
selected all existing groups in the work file will be changed to the type 
defined in the Change To menu.

The first entry in the Change To menu is "No Change".  When this is 
selected, no change will be made when the Apply button is pressed.  This is 
to prevent accidental group changes.

