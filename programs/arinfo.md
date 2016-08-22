---
title: ARINFO
layout: default
---

ARINFO scans a McIDAS AREA file header and outputs the requested information.
  The minimum and maximum values of the data block are also provided with the
  '-a' option.
  
# Input Parameters
    
      arinfo [-option] areafile
    
      options:  -a   dump all, the entire header
                -b   display the 'band' number
                -d   date in YYMMDD form
                -i   image type (VIS, IR, WV)
                -j   julian date, YYJDY
                -n   navigation type
                -r   resolution of image
                -s   satellite name
                -t   time in HHMM form
                -m   min/max pixel values
