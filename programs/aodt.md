---
title: AODT
layout: default
---

AODT makes the appropriate calls into the CIMSS AODT library to
calculate tropical cyclone intensity. The results are output to the
screen as well as the history file.


  - Use of default history file will only provide user
with CI value (which is actually the RAW T#).
NO TIME AVERAGING OR OTHER ADJUSTMENTS WILL BE PERFORMED,
and any output will only list this CI (raw T#) value.
  - Use of default history file is only possible when AODT 
analysis is performed (ie, LIST and/or DELETE options disabled).
  - If either LIST=YES or DELETE=YES
AODT analysis will NOT be performed on current image.
  - If a record is modified/added within an existing history
file, all subsequent records within the history file
will be recalculated using the new/modified AODT record.
  - If DATE is provided in conjunction with LIST *AND*
DELETE keywords, DATE will apply ONLY to the DELETE
keyword (and a LIST will be drawn/listed for
the entire history file (defaults)).


# Examples

    aodt -c nmap2.cpf IR_19990915_1045

performs the AODT analysis on the image file IR_19990915_1045
  (located in the current working directoy) using the latitude and
  longitude in the cpf file "nmap2.cpf". The history file will be
	  the default history file "AODTDUMP.AODT".

    aodt -c 29.4,-78.8 -y $AODTHIST/floyd $SAT/GOES-E/TropAtl_8km/IR/IR_19990915_1045

performs the AODT analysis on the image file IR_19990915_1045 
	  (located in the directoy "$SAT/GOES-E/TropAtl_8km/IR") using a 
	  latitude of 29.4 and longitude of -78.8. The history file will 
	  be saved to the file "$AODTHIST/floyd".

