# The seawater package

Adapted from the seawater package by Bjørn Ådlandsvik at the following link:

https://github.com/bjornaa/seawater/

# Original documentation from Bjørn Ådlandsvik

### Introduction

The seawater module provides basic functions in Python for physical
properties of sea water. The scope is similar to the MATLAB toolboxes
SEAWATER from CSIRO and parts of OCEANS from Woods Hole Institute.

Most of the formulas used are taken from Unesco's joint panel on
oceanographic tables and standards, UNESCO 1981 and UNESCO 1983.

The present version is 1.2, released 22 January 2015
This is an minor update from version 1.1 from 2004.
It is now compatible with python 3 and 2.7.

With the new Gibbs function based equation of state
`TEOS-10 <http://www.teos-10.org/>`_ this seawater package is becoming obsolete.
It is retained here under the MIT-license for backwards compability.
Filipe Fernandes is leading the python implentation of the new equation of
state in python, `python-gsw <https://github.com/TEOS-10/python-gsw>`_.

### User documentation

The functions are mainly polynomials, with an occasional fractional
exponent. The functions can therefore be used traditionally without NumPy to
compute a single value. With NumPy the functions act like "ufuncs" in the
NumPy sence. This means that they can take array arguments and return an
array of the same shape.


Public functions::

 Density related
   dens(S,T,P)           Density of sea water              kg/m**3
   svan(S,T,P)           Specific volume anomaly           m**3/kg
   sigma(S,T,P)          Density anomaly                   kg/m**3
   drhodt(S,T,P)         Temperature derivative of density kg/(K*m**3)
   alpha(S,T,P)          Thermal expansion coefficient     1/K
   drhods(S,T,P)         Salinity derivative of density    kg/m**3
   beta(S,T,P)           Salinity expansion coefficient

 Salinity related
   salt(R,T,P)           Salinity
   cond(S,T,P)           Conductivity ratio

 Heat related
   heatcap(S,T,P)        Heat capacity                     J/(kg*K)
   adtgrad(S,T,P)        Adiabatic lapse rate              K/dbar
   temppot(S,T,P,Pref)   Potential temperature             °C
   temppot0(S,T,P)       Potential temperature             °C

 Miscellaneous
   freezept(S,P)         Freezing point                    °C
   soundvel(S,T,P)       Sound velocity                    m/s
   depth(P,lat)          Depth                             m

 Arguments:
   S                     Salinity
   T                     Temperature                       °C
   P                     Pressure                          dbar
   R                     Conductivity ratio
   Pref                  Reference pressure                dbar
   lat                   Latitude                          deg


### Test scripts

The test directory contains several test scripts. The script test.py tests some
standard values in the UNESCO 1983 report.  The script testwater.py prints out
part of table A3.1 in the book by Gill (1982). To recreate the potential
temperature values the alternative function temppot0, implementing an
algorithm from Bryden (1973), is used.

The scripts testdens, testsalt, testheat, and testmisc computes and prints
tables from the UNESCO 1983 report.

### Install

The seawater package is written in pure Python and should work on any system.
NumPy is not necessary, but highly recommended. To install the package, use
the commands:

    python setup.py build
    python setup.py install

(the install commmand may need root access).

### References

Bryden, 1973
New polynomials for thermal expansion, adiabatic temperature gradient
and potential temperature gradient of sea water, Deep-Sea Res. 20, 401-408

A. E. Gill, 1982
Atmosphere-Ocean Dynamics, Academic Press.

UNESCO 1981, Tenth report of the joint panel on oceanographic tables
 and standards, Unesco technical papers in marine science, 36.

UNESCO 1983, N.P. Fofonoff and R.C. Millard Jr.,
Algorithms for computation of fundamental properties of seawater,
Unesco technical papers in marine science, 44.

### Author
::

  Bjørn Ådlandsvik <bjorn@imr.no>
  Institute of Marine Research
  Version 1.1 November 2004
  Version 1.2 January 2015
