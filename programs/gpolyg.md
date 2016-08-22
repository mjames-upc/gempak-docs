---
title: GPOLYG
layout: default
---


GPOLYG processes gridded data to produce small craft advisory (SCA), 
gale, storm and hurricane watch or warning polygons and Common 
Alerting Protocol (CAP) message over the water.  To execute the 
program properly, the grids need to be on CED projection. For grid 
points whose wind speed exceeds specific category, they will be grouped 
together.  The final warning polygons are generated by clipping the
group areas with the forecast zones.

The execution of the program is controlled by user inputs in the 
following format,

    gpolyg
      grid file
      grid time
      alias for forecast zone
      grid area

where grid file is in CED; grid time is in the form of 
`080804/1200f12:080804/1200f36` for 0 to 24 h warning polygons or 
`080804/1200f36:080804/1200f60` for 24 to 48 h watch polygons; the
forecast zone can be `opc_atl`, `opc_pac` or `tpc_atl`; and the grid 
area can be `dset`, `grid` or a pair of latitudes and longitudes covers 
the lower left and upper right corners.

Two outputs are generated after execution of the program: a set of
VGF files which plot warning polygons and XML files which contain 
vertices (latitudes/longitude) of the polygons in CAP format.

A parameter table, `poly_parm.tbl`, which includes various parameters 
specified by users.  See prolog for the usage of the parameters.