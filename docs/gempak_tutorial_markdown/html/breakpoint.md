
Breakpoint 4, vi_vint (ip=3, cmn_data=..., ovcbuf1=..., ovcbuf2=..., 
    rlnpi=..., rlnpo=..., valu=..., iret=0) at vivint.f:100
100		    DO WHILE ( .not. done )
(gdb) p done
(gdb) p vclo
$23 = (1037.44104, 1000.00012, 975.000244, 950, 925.000183, 900.000122, 874.999939, 850.000061, 825.000122, 800.000061, 775, 750.000061, 725, 699.999939, 675.000061, 650.000122, 625.000061, 600.000061, 575.000061, 550.000061, 524.999939, 500.000061, 475, 450.000031, 425.000031, 400.000031, 375.000031, 349.999969, 325.000061, 300.000031, 275.000031, 250.000031, 225.000015, 200.000015, 174.999985, 150.000015, 125.000008, 100.000008, 69.9999924, 50.0000038, 30.0000019, 20, 10, 7.00000048, 5, 3, 2, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0)
(gdb) p vchi
$24 = (500.966095, 500.966095, 500.966095, 500.966095, 500.966095, 500.966095, 500.966095, 500.966095, 500.966095, 500.966095, 500.966095, 500.966095, 500.966095, 500.966095, 500.966095, 500.966095, 500.966095, 500.966095, 500.966095, 500.966095, 500.966095, 500.000061, 475, 450.000031, 425.000031, 400.000031, 375.000031, 349.999969, 325.000061, 300.000031, 275.000031, 250.000031, 225.000015, 200.000015, 174.999985, 150.000015, 125.000008, 100.000008, 69.9999924, 50.0000038, 30.0000019, 20, 10, 7.00000048, 5, 3, 2, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0)

 ip:     3  vclo(kinm1) =    1037.4410      | vchi (kin)=   500.96609     kinm1:     1  kin:     2
 ip:     3  vclo(kinm1) =    1000.0001      | vchi (kin)=   500.96609     kinm1:     2  kin:     3
 ip:     3  vclo(kinm1) =    975.00024      | vchi (kin)=   500.96609     kinm1:     3  kin:     4
 ip:     3  vclo(kinm1) =    950.00000      | vchi (kin)=   500.96609     kinm1:     4  kin:     5
 ip:     3  vclo(kinm1) =    925.00018      | vchi (kin)=   500.96609     kinm1:     5  kin:     6
 ip:     3  vclo(kinm1) =    900.00012      | vchi (kin)=   500.96609     kinm1:     6  kin:     7
 ip:     3  vclo(kinm1) =    874.99994      | vchi (kin)=   500.96609     kinm1:     7  kin:     8
 ip:     3  vclo(kinm1) =    850.00006      | vchi (kin)=   500.96609     kinm1:     8  kin:     9
 ip:     3  vclo(kinm1) =    825.00012      | vchi (kin)=   500.96609     kinm1:     9  kin:    10
 ip:     3  vclo(kinm1) =    800.00006      | vchi (kin)=   500.96609     kinm1:    10  kin:    11
 ip:     3  vclo(kinm1) =    775.00000      | vchi (kin)=   500.96609     kinm1:    11  kin:    12
 ip:     3  vclo(kinm1) =    750.00006      | vchi (kin)=   500.96609     kinm1:    12  kin:    13
 ip:     3  vclo(kinm1) =    725.00000      | vchi (kin)=   500.96609     kinm1:    13  kin:    14
 ip:     3  vclo(kinm1) =    699.99994      | vchi (kin)=   500.96609     kinm1:    14  kin:    15
 ip:     3  vclo(kinm1) =    675.00006      | vchi (kin)=   500.96609     kinm1:    15  kin:    16
 ip:     3  vclo(kinm1) =    650.00012      | vchi (kin)=   500.96609     kinm1:    16  kin:    17
 ip:     3  vclo(kinm1) =    625.00006      | vchi (kin)=   500.96609     kinm1:    17  kin:    18
 ip:     3  vclo(kinm1) =    600.00006      | vchi (kin)=   500.96609     kinm1:    18  kin:    19
 ip:     3  vclo(kinm1) =    575.00006      | vchi (kin)=   500.96609     kinm1:    19  kin:    20
 ip:     3  vclo(kinm1) =    550.00006      | vchi (kin)=   500.96609     kinm1:    20  kin:    21
 ip:     3  vclo(kinm1) =    524.99994      | vchi (kin)=   500.00006     kinm1:    21  kin:    22
 ip:     3  vclo(kinm1) =    500.00006      | vchi (kin)=   475.00000     kinm1:    22  kin:    23
 ip:     3  vclo(kinm1) =    475.00000      | vchi (kin)=   450.00003     kinm1:    23  kin:    24
 ip:     3  vclo(kinm1) =    450.00003      | vchi (kin)=   425.00003     kinm1:    24  kin:    25
 ip:     3  vclo(kinm1) =    425.00003      | vchi (kin)=   400.00003     kinm1:    25  kin:    26
 ip:     3  vclo(kinm1) =    400.00003      | vchi (kin)=   375.00003     kinm1:    26  kin:    27
 ip:     3  vclo(kinm1) =    375.00003      | vchi (kin)=   349.99997     kinm1:    27  kin:    28
 ip:     3  vclo(kinm1) =    349.99997      | vchi (kin)=   325.00006     kinm1:    28  kin:    29
 ip:     3  vclo(kinm1) =    325.00006      | vchi (kin)=   300.00003     kinm1:    29  kin:    30
 ip:     3  vclo(kinm1) =    300.00003      | vchi (kin)=   275.00003     kinm1:    30  kin:    31
 ip:     3  vclo(kinm1) =    275.00003      | vchi (kin)=   250.00003     kinm1:    31  kin:    32
 ip:     3  vclo(kinm1) =    250.00003      | vchi (kin)=   225.00002     kinm1:    32  kin:    33
 ip:     3  vclo(kinm1) =    225.00002      | vchi (kin)=   200.00002     kinm1:    33  kin:    34
 ip:     3  vclo(kinm1) =    200.00002      | vchi (kin)=   174.99998     kinm1:    34  kin:    35
 ip:     3  vclo(kinm1) =    174.99998      | vchi (kin)=   150.00002     kinm1:    35  kin:    36
 ip:     3  vclo(kinm1) =    150.00002      | vchi (kin)=   125.00001     kinm1:    36  kin:    37
 ip:     3  vclo(kinm1) =    125.00001      | vchi (kin)=   100.00001     kinm1:    37  kin:    38
 ip:     3  vclo(kinm1) =    100.00001      | vchi (kin)=   69.999992     kinm1:    38  kin:    39
 ip:     3  vclo(kinm1) =    69.999992      | vchi (kin)=   50.000004     kinm1:    39  kin:    40
 ip:     3  vclo(kinm1) =    50.000004      | vchi (kin)=   30.000002     kinm1:    40  kin:    41
 ip:     3  vclo(kinm1) =    30.000002      | vchi (kin)=   10.000000     kinm1:    41  kin:    43

 kpt(kkk):            2  kkk:            2
 ip:            3  vclo(kinm1) =    1037.4410      | vchi (kin)=   500.96609     kinm1:            1  kin:            2
 kpt(kkk):            3  kkk:            3
 ip:            3  vclo(kinm1) =    1000.0001      | vchi (kin)=   500.96609     kinm1:            2  kin:            3
 kpt(kkk):            4  kkk:            4
 ip:            3  vclo(kinm1) =    975.00024      | vchi (kin)=   500.96609     kinm1:            3  kin:            4
 kpt(kkk):            5  kkk:            5
 ip:            3  vclo(kinm1) =    950.00000      | vchi (kin)=   500.96609     kinm1:            4  kin:            5
 kpt(kkk):            6  kkk:            6
 ip:            3  vclo(kinm1) =    925.00018      | vchi (kin)=   500.96609     kinm1:            5  kin:            6
 kpt(kkk):            7  kkk:            7
 ip:            3  vclo(kinm1) =    900.00012      | vchi (kin)=   500.96609     kinm1:            6  kin:            7
 kpt(kkk):            8  kkk:            8
 ip:            3  vclo(kinm1) =    874.99994      | vchi (kin)=   500.96609     kinm1:            7  kin:            8
 kpt(kkk):            9  kkk:            9
 ip:            3  vclo(kinm1) =    850.00006      | vchi (kin)=   500.96609     kinm1:            8  kin:            9
 kpt(kkk):           10  kkk:           10
 ip:            3  vclo(kinm1) =    825.00012      | vchi (kin)=   500.96609     kinm1:            9  kin:           10
 kpt(kkk):           11  kkk:           11
 ip:            3  vclo(kinm1) =    800.00006      | vchi (kin)=   500.96609     kinm1:           10  kin:           11
 kpt(kkk):           12  kkk:           12
 ip:            3  vclo(kinm1) =    775.00000      | vchi (kin)=   500.96609     kinm1:           11  kin:           12
 kpt(kkk):           13  kkk:           13
 ip:            3  vclo(kinm1) =    750.00006      | vchi (kin)=   500.96609     kinm1:           12  kin:           13
 kpt(kkk):           14  kkk:           14
 ip:            3  vclo(kinm1) =    725.00000      | vchi (kin)=   500.96609     kinm1:           13  kin:           14
 kpt(kkk):           15  kkk:           15
 ip:            3  vclo(kinm1) =    699.99994      | vchi (kin)=   500.96609     kinm1:           14  kin:           15
 kpt(kkk):           16  kkk:           16
 ip:            3  vclo(kinm1) =    675.00006      | vchi (kin)=   500.96609     kinm1:           15  kin:           16
 kpt(kkk):           17  kkk:           17
 ip:            3  vclo(kinm1) =    650.00012      | vchi (kin)=   500.96609     kinm1:           16  kin:           17
 kpt(kkk):           18  kkk:           18
 ip:            3  vclo(kinm1) =    625.00006      | vchi (kin)=   500.96609     kinm1:           17  kin:           18
 kpt(kkk):           19  kkk:           19
 ip:            3  vclo(kinm1) =    600.00006      | vchi (kin)=   500.96609     kinm1:           18  kin:           19
 kpt(kkk):           20  kkk:           20
 ip:            3  vclo(kinm1) =    575.00006      | vchi (kin)=   500.96609     kinm1:           19  kin:           20
 kpt(kkk):           21  kkk:           21
 ip:            3  vclo(kinm1) =    550.00006      | vchi (kin)=   500.96609     kinm1:           20  kin:           21
 kpt(kkk):           22  kkk:           22
 ip:            3  vclo(kinm1) =    524.99994      | vchi (kin)=   500.00006     kinm1:           21  kin:           22
 kpt(kkk):           23  kkk:           23
 ip:            3  vclo(kinm1) =    500.00006      | vchi (kin)=   475.00000     kinm1:           22  kin:           23
 kpt(kkk):           24  kkk:           24
 ip:            3  vclo(kinm1) =    475.00000      | vchi (kin)=   450.00003     kinm1:           23  kin:           24
 kpt(kkk):           25  kkk:           25
 ip:            3  vclo(kinm1) =    450.00003      | vchi (kin)=   425.00003     kinm1:           24  kin:           25
 kpt(kkk):           26  kkk:           26
 ip:            3  vclo(kinm1) =    425.00003      | vchi (kin)=   400.00003     kinm1:           25  kin:           26
 kpt(kkk):           27  kkk:           27
 ip:            3  vclo(kinm1) =    400.00003      | vchi (kin)=   375.00003     kinm1:           26  kin:           27
 kpt(kkk):           28  kkk:           28
 ip:            3  vclo(kinm1) =    375.00003      | vchi (kin)=   349.99997     kinm1:           27  kin:           28
 kpt(kkk):           29  kkk:           29
 ip:            3  vclo(kinm1) =    349.99997      | vchi (kin)=   325.00006     kinm1:           28  kin:           29
 kpt(kkk):           30  kkk:           30
 ip:            3  vclo(kinm1) =    325.00006      | vchi (kin)=   300.00003     kinm1:           29  kin:           30
 kpt(kkk):           31  kkk:           31
 ip:            3  vclo(kinm1) =    300.00003      | vchi (kin)=   275.00003     kinm1:           30  kin:           31
 kpt(kkk):           32  kkk:           32
 ip:            3  vclo(kinm1) =    275.00003      | vchi (kin)=   250.00003     kinm1:           31  kin:           32
 kpt(kkk):           33  kkk:           33
 ip:            3  vclo(kinm1) =    250.00003      | vchi (kin)=   225.00002     kinm1:           32  kin:           33
 kpt(kkk):           34  kkk:           34
 ip:            3  vclo(kinm1) =    225.00002      | vchi (kin)=   200.00002     kinm1:           33  kin:           34
 kpt(kkk):           35  kkk:           35
 ip:            3  vclo(kinm1) =    200.00002      | vchi (kin)=   174.99998     kinm1:           34  kin:           35
 kpt(kkk):           36  kkk:           36
 ip:            3  vclo(kinm1) =    174.99998      | vchi (kin)=   150.00002     kinm1:           35  kin:           36
 kpt(kkk):           37  kkk:           37
 ip:            3  vclo(kinm1) =    150.00002      | vchi (kin)=   125.00001     kinm1:           36  kin:           37
 kpt(kkk):           38  kkk:           38
 ip:            3  vclo(kinm1) =    125.00001      | vchi (kin)=   100.00001     kinm1:           37  kin:           38
 kpt(kkk):           39  kkk:           39
 ip:            3  vclo(kinm1) =    100.00001      | vchi (kin)=   69.999992     kinm1:           38  kin:           39
 kpt(kkk):           40  kkk:           40
 ip:            3  vclo(kinm1) =    69.999992      | vchi (kin)=   50.000004     kinm1:           39  kin:           40
 kpt(kkk):           41  kkk:           41
 ip:            3  vclo(kinm1) =    50.000004      | vchi (kin)=   30.000002     kinm1:           40  kin:           41
 kpt(kkk):           43  kkk:           42
 ip:            3  vclo(kinm1) =    30.000002      | vchi (kin)=   10.000000     kinm1:           41  kin:           43
 
 
 
 
             IF ( .not. havqqq ) THEN
                CALL VI_GETQ ( lev, 0, cmn_data, rlnpi,
     +                         cmn_data( sphbuf_indx ),
     +                         cmn_data( tmpbuf_indx ), hgtbuf, iret )
            END IF

	iret = -12
	
