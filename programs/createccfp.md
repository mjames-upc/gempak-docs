---
title: CREATECCFP
layout: default
---

CREATECCFP reads/scans 3 VGF files and creates an ASCII file based on
the content of the VGF files. The output text file contains information
for the CCFP product.

The output ASCII CCFP product is sent to standard output and should be
directed to the appropriate filename.
# Input Parameters

    createccfp YYMMDD/HHHH vgf_file1 vgf_file2 vgf_file3

      createccfp		Program name
      YYMMDD/HHHH		Cycle of forecast
      vgf_fileN		VGF file number N


# Example

    createccfp YYMMDD/HHHH fcsthr2 fcsthr4 fcsthr6 > YYMMDDHH.ccfp

reads 3 forecast hour files and creates the CCFP text 
  file YYMMDDHH.ccfp.
