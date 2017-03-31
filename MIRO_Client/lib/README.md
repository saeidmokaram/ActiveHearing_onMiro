# Sinesweep

Python translation of MATLAB code for log sine sweep generation and impulse response estimation. The original MATLAB code is here

https://uk.mathworks.com/matlabcentral/fileexchange/29187-swept-sine-analysis

## Install Python dependencies

pip install librosa
pip install docopt

## Usage

#### synth_sweep.py -- generates a sine sweep and inverse filter

    python synth_sweep.py testsweep

Generates 

* testsweep.wav  -- wave file storing sine sweep
* testsweep.inv.npy -- numpy file containing inverse filter

    python synth_sweep.py --help

To see full list of options, eg. setting the start and end frequency and duration.

#### extract_ir.py -- applies inverse filtering to recorded sweep

    python extract_ir.py recordedsweep.wav testsweep.inv.npy response.npy

Inputs

* recordedsweep.wav -- wav file containing sine sweep recording
* testsweep.inv.npy -- numpy file containing inverse filter that was generated by synth_sweep.py

Generates

* respnose.npy -- numpy file containing impulse response