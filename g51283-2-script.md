```python
reinitialize
set bg_rgb, white
set ray_opaque_background, 1

load g51283_dip.pdb
load g51283_swiss_tetra.pdb
set_name g51283_dip, dip
set_name g51283_swiss_tetra, tetra
align tetra, dip
hide
as cartoon
color green, dip
color green, tetra

select unique_dip, (dip and resi 44,49,89,151,496)
select unique_tetra, (tetra and resi 44,49,89,151,496)
color red, unique_dip
color marine, unique_tetra
show sticks, unique_dip
show sticks, unique_tetra

select interactionDNA, (resi 73,205,212,348,224-229)
select Mgbindingsite, (resi 12,131,133)
select activesite, (resi 346)
color pink, activesite
show sticks, activesite
color cyan, interactionDNA
color magenta, Mgbindingsite

color atomic, (not elem C)

set_view (\
    -0.138898030,   -0.990164816,   -0.016662110,\
    -0.002223504,    0.017136255,   -0.999848723,\
     0.990305424,   -0.138839781,   -0.004582308,\
     0.000010699,    0.000007652, -296.118774414,\
     1.730719686,    0.820641458,    4.533525944,\
   212.559158325,  379.678314209,  -20.000000000 )
ray 5120,2880
png full-cartoon, dpi=600

set_view (\
    -0.468370408,   -0.852462769,   -0.232224435,\
    -0.047418118,    0.286707014,   -0.956841767,\
     0.882255077,   -0.437146038,   -0.174704894,\
    -0.000002578,   -0.000001820,  -92.593757629,\
   -24.354955673,    3.948061228,   12.582652092,\
     9.034208298,  176.153396606,  -20.000000000 )
ray 5120,2880
png mutation1-cartoon, dpi=600

set_view (\
     0.716444910,   -0.658565402,    0.230199054,\
    -0.617914200,   -0.445859939,    0.647599041,\
    -0.323850244,   -0.606212854,   -0.726372778,\
    -0.000403718,   -0.000228956,  -69.193016052,\
    23.173585892,  -16.478096008,  -43.466236115,\
    50.618999481,   87.714958191,  -20.000000000 )
ray 5120,2880
png mutation2-cartoon, dpi=600

set_view (\
     0.302471817,    0.652828336,    0.694491088,\
     0.701890111,    0.340402246,   -0.625674307,\
    -0.644869208,    0.676706374,   -0.355254591,\
    -0.000040591,    0.000120223, -103.243713379,\
    27.633094788,  -10.556243896,  -14.055576324,\
    84.505241394,  121.975921631,  -20.000000000 )
ray 5120,2880
png mutation3-cartoon, dpi=600




apbs_surface dip
apbs_surface tetra
set surface_quality, 1
set_view (\
    -0.479534894,   -0.815462530,    0.324135959,\
    -0.136808470,   -0.295386434,   -0.945528805,\
     0.866790831,   -0.497760683,    0.030085724,\
     0.000004031,    0.000041425, -354.719848633,\
    17.066713333,    2.790887833,   10.692754745,\
   271.158966064,  438.278076172,  -20.000000000 )
ray 5120,2880
png apbs-dip, dpi=600

ray 5120,2880
png apbs-tetra, dpi=600