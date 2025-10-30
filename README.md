This is a patched version of tune-s2 for enabling USALS dish positioning for users south of the equator. 
Previously, tune-s2 would steer the dish in the wrong direction for us folks down in the southern hemisphere. 
All other functionality is identical to crazycats tune-S2 repository. Tested and working on DragonOS FocalX R37.

## Building
```
cd
git clone https://github.com/RobVK8FOES/tune-s2.git
cd tune-s2
make
```

## Usage Example
```
cd tune-s2
./tune-s2 12310 H 5832 -lnb UNIVERSAL -lat -12.36 -long 130.89 -usals 166.0

./tune-s2      = Name of binary
12310          = Tune to a transponder on 12.310 GHz
H              = Horizontal Polarisation
5832           = Symbol rate of 5832 ms/s
-lnb UNIVERSAL = Universal type of LNB
-lat -12.36    = -12.36 Lattitude
-long 130.89   = 130.89 Longitude
-usals 166.0   = 166E USALS Oribital Position
```
Run the binary with no arguments to see help file:
```
cd tune-s2
./tune-s2
usage: tune-s2 12224 V 20000 [options]
        -adapter N     : use given adapter (default 0)
        -frontend N    : use given frontend (default 0)
        -2             : use 22khz tone
        -committed N   : use DiSEqC COMMITTED switch position N (1-4)
        -uncommitted N : use DiSEqC uncommitted switch position N (1-4)
        -servo N       : servo delay in milliseconds (20-1000, default 20)
        -gotox NN      : Drive Motor to Satellite Position NN (0-99)
        -usals N.N     : orbital position
        -long N.N      : site long
        -lat N.N       : site lat
        -lnb lnb-type  : STANDARD, UNIVERSAL, DBS, CBAND or 
        -system        : System DVB-S or DVB-S2
        -modulation    : modulation BPSK QPSK 8PSK
        -fec           : fec 1/2, 2/3, 3/4, 3/5, 4/5, 5/6, 6/7, 8/9, 9/10, AUTO
        -rolloff       : rolloff 35=0.35 25=0.25 20=0.20 0=UNKNOWN
        -inversion N   : spectral inversion (OFF / ON / AUTO [default])
        -pilot N       : pilot (OFF / ON / AUTO [default])
        -mis N         : MIS #
        -quit          : quit after tuning, used to time lock aquisition        -help          : help
```

## Installation
```
cd tune-s2
sudo make install
```
