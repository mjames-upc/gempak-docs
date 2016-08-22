	
	Breakpoint 3, vi_getz (lev=42, ovrwrt=.TRUE., update=.TRUE., cmn_data=..., 
	    sfcval=..., rlnpi=..., valu=..., plast=..., tlast=..., zlast=..., hgtbuf=..., 
	    zgrd=..., iret=-12) at vigetz.f:118
	118		    DO ij = 1, kxky
	(gdb) p iret
	$6 = -12
	(gdb) l
	113		    IF ( .not. havqqq ) THEN
	114	                CALL VI_GETQ ( lev, 0, cmn_data, rlnpi, 
	115	     +                         cmn_data( sphbuf_indx ), 
	116	     +                         cmn_data( tmpbuf_indx ), hgtbuf, iret )
	117		    END IF
	118		    DO ij = 1, kxky
	119			IF ( .not. ERMISS ( valu (ij,lev) ) .and.
	120	     +		     .not. ERMISS ( hgtbuf (ij) ) ) THEN
	121			    tlast (ij) = valu (ij,lev) *
	122	     +				 ( 1. + .608 * hgtbuf (ij) )
	(gdb) 
	
