# Additional tools for NIST REFPROP MATLAB function

## Description

This repository contains the MATLAB function `refprop` which is a
backend to the [NIST REFPROP](http://www.nist.gov/srd/nist23.cfm)
MATLAB function `refpropm`, itself a backend to the FORTRAN
subroutines that are used by NIST REFPROP. Those FORTRAN routines are
compiled as a MATLAB binary (mex file). Unfortunately, the syntax of
this first backend is not handy and differs depending on the output(s)
the user requests. The `refprop` function is an effort to soften the
drawbacks of `refpropm`. Notably, it allows:

* To use arrays as inputs;
* To compute pure fluids and mixtures properties with the same syntax;
* To deal with experimental data more easily, with options for
  uncertainties;

## Usage

This function relies on the NIST REFPROP MATLAB function. Logically,
`refpropm` needs to be present in your MATLAB PATH and to be
functional. For details about the syntax of the function, see the
MATLAB help:

    help refprop

## Run the tests

In order to run the tests, you need the
[MATLAB xUnit Test Framework](http://www.mathworks.com/matlabcentral/fileexchange/22846-matlab-xunit-test-framework),
and simply need to run the command `runtests` from the `tests` folder.

## Future work

For now, this is the only function provided as additional tools. Feel
free to fork and improve the current code base, as it relies on a
pretty inefficient way to call the initial function (with an `eval`, as
the number of outputs depends on the user requirements). The best way
will be in the future to develop a completely new interface to the
FORTRAN subroutines. This is a next step.

## Author, Copyright and License

© 2013 Jean-Baptiste Carré (<jbc@0x1d.org>).

All software and files in this repository are licensed under the GNU
General Public License, either version 3 of the License, or (at your
option) any later version.
