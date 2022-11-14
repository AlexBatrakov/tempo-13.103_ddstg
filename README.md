# Tempo software with the implemented DDSTG model

1. Installation gide
------------------------
To make Tempo:

    ./prepare (only if compiling from a CVS checkout)
    ./configure [any desired options]
    make
    make install (optional)
    
Install the environment veriable $TEMPO to the folder with Tempo software and add it to the $PATH.

Extract files in all subfolders of "data_ddstg" folder so that Tempo has an access to the precalulated grids.

    find . -name "*.zip" | while read filename; do unzip -o -d "`dirname "$filename"`" "$filename"; done;
    find . -type f -name '*.zip' -delete

For further documentation and details on installation and testing, see
either of the following:

$TEMPO/doc/index.html within the tempo distribvution
http://tempo.sourceforge.net

A permanent reference URL for tempo is at the Astrophysics Source Code Library:
http://www.ascl.net/1509.002
  
2. Quick Guide
------------------------

This Tempo version contains the DDSTG model, developed for testing scalar-tensor gravity (STG) theories with timing of binary pulsars. 

The added files are:

 - bnryddstg.f contains formulae to caclulate relativistic time delays
 - mass2ddstg.f contains formulae to calculate post-Keplerian parameters in STG
 - ddstg_tools.f contains routines to read and interpolate grids of gravitational form-factors

Other modified files contain "DDSTG" comment in the modified segment of the code.

The folder "data_ddstg" contains subfolders for 11 different equations of state (EOS). Each subfolder consists of files with grids of masses and gravitational form-factors pracalcilated for a particular EOS. All files in the subfolders are compressed and need to be extracted to the same folder so that Tempo could read the grids.

The folder "arm_fix" contains a modified file "bnrydds.f" which can be used to compile Tempo on Macs with ARM processors (M1 and M2). ARM processors treat the long double (80 or 120-bit) format as the double (64-bit) format. All the Tempo code is written with 64-bit numbers except DDS model. To compile Tempo on ARM-based machines one need to substitute "bnrydds.f" file with a compatible version.

DDSTG model uses additional parameters in the par-file:

 - ALPHA0
 - BETA0
 - EOS
 - COMP_TYPE

Exact derivatives and corrections dut to the mass dependence of gravitiational form-factors

