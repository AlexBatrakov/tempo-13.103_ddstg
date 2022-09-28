# Tempo software with the DDSTG model implementation

1. From original tempo repositorium
------------------------
To make Tempo:

    ./prepare (only if compiling from a CVS checkout)
    ./configure [any desired options]
    make
    make install (optional)

For further documentation and details on installation and testing, see
either of the following:

$TEMPO/doc/index.html within the tempo distribvution
http://tempo.sourceforge.net

A permanent reference URL for tempo is at the Astrophysics Source Code Library:
http://www.ascl.net/1509.002
  
2. Quick Guide
------------------------

This Tempo version contains the DDSTG model, developed for testing scalar-tensor gravity (STG) theories with binary pulsa timing. 
The added files are:

 - bnryddstg.f contains formulae to caclulate relativistic time delays
 - mass2ddstg.f contains formulae to calculate post-Keplerian parameters in STG
 - ddstg_tools.f contains routines to read and interpolate grids of gravitational form-factors
 - other files with "DDSTG" comment

