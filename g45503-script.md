```python
reinitialize
set bg_rgb, white
set ray_opaque_background, 1

load g45503_dip.pdb
load g45503_swiss_tetra.pdb
set_name g45503_dip, dip
set_name g45503_swiss_tetra, tetra
align tetra, dip
hide
as cartoon
color green, dip
color green, tetra
color cyan, (dip and resi 117-300)
color cyan, (tetra and resi 117-300)
color pink, (dip and resi 248-251)
color pink, (tetra and resi 248-251)

select unique_dip, (dip and resi 59,359,377,460,465,511,539,544)
select unique_tetra, (tetra and resi 59,359,377,460,465,511,539,544)

color red, unique_dip
color marine, unique_tetra
show sticks, unique_dip
show sticks, unique_tetra
color atomic, (not elem C)

set_view (\
    -0.465261757,    0.520718396,    0.715807974,\
    -0.632167101,    0.370568961,   -0.680469394,\
    -0.619591951,   -0.769108295,    0.156771451,\
     0.000066057,   -0.000046920, -200.144332886,\
    12.734083176,   20.093584061,   15.480380058,\
   126.321830750,  273.995208740,  -20.000000000 )
ray 5120,2880
png full-cartoon, dpi=600

set_view (\
     0.322117448,   -0.611055017,    0.723084211,\
     0.213034078,   -0.697415829,   -0.684265733,\
     0.922421873,    0.374457121,   -0.094472513,\
     0.000015298,    0.000001425, -124.105087280,\
    14.091292381,   -1.975067019,   39.585731506,\
    91.027366638,  157.181427002,  -20.000000000 )
ray 5120,2880
png mutantloop-cartoon, dpi=600

set_view (\
    -0.523030043,   -0.025989791,    0.851916969,\
    -0.811515272,    0.320721775,   -0.488442093,\
    -0.260536939,   -0.946818829,   -0.188837305,\
     0.000043549,   -0.000015870, -117.982269287,\
    10.855715752,    5.058562279,   -4.760370255,\
    84.905349731,  151.059402466,  -20.000000000 )
ray 5120,2880
png mutanthelix-cartoon, dpi=600

show sticks, resi 527
color atomic, (not elem C)
set_view (\
    -0.956378877,    0.261203170,   -0.130804434,\
     0.189685345,    0.895805538,    0.401935309,\
     0.222161829,    0.359592348,   -0.906275868,\
     0.000044029,    0.000008359,  -66.880279541,\
    14.625748634,    8.756261826,  -11.682707787,\
    58.341575623,   75.415290833,  -20.000000000 )
ray 5120,2880
png dissulf-cartoon, dpi=600

apbs_surface dip
apbs_surface tetra
set surface_quality, 1

set_view (\
     0.204236418,    0.346340626,    0.915605783,\
    -0.972405076,    0.179500535,    0.149007127,\
    -0.112744913,   -0.920777321,    0.373448670,\
     0.000000179,   -0.000141785, -299.528289795,\
    15.618663788,    4.766437531,   19.270378113,\
   -26.269886017,  625.329406738,  -20.000000000 )
ray 5120,2880
png apbs-dip, dpi=600

ray 5120,2880
png apbs-tetra, dpi=600
