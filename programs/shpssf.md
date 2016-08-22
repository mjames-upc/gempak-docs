---
title: SHPSSF
layout: default
---


    shpssf -s 0.005 -i hicnus.ssf c_18nv03

the program creates high resolution map files from the shapefile 
`c_18nv03`. The strip tolerance is 0.005.

    shpssf -a mzcn.ssf c_18nv03 mz15jl04

the program combines shapefile `c_18nv03` and `mz15jl04` together, and
creates top, high, medium and low resolution map files with file name
`tpmzcn.ssf`, `himzcn.ssf`, `memzcn.ssf` and `lomzcn.ssf` respectively.
Overlapped map lines are not stripped.
