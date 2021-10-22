=============
PVLab Package
=============

Description
-----------
PVLAB is a project devoted to the development and improvement of scientific 
software for the measurement, calibration and modeling of the performance of 
photoltaic devices and solar sensors. PVLAB package was born from the efforts 
made to perform the data treatment during the calibration of pyranometers at 
the Laboratory of Photovoltaic Solar Energy (PVLAb), in the Research Center 
for Energy, Environment and Technology (CIEMAT) in Madrid, Spain. In next 
releases, PVLAB will be providing sets of tools, mainly consisting in classes
and functions, to perform the data treatment for the calibration of 
pyranometers and other type of solar sensors and photovoltaic devices.
Eventually, ``pvlab`` will try to widen its scope to further calibration
procedures of solar sensors and photovoltaic devices.

History
-------
The origin of ```pvlab`` is a python tool, named ``calibration``,
developed in 2019 in the laboratory |lab| at the |ciemat| for its
own use. It was originally designed to manage the big amount of data
generated during the outdoor measurements when performing the routine
calibration of pyranometers.

Soon, both the *python programming language* and the ``calibration``
tool proved to be quick and reliable methods for data treatment.
Gradually, the code grew in complexity, whereas new functionalities were
enabled. Indeed, to the basic requirements of *data I/O* and a first
block of calculations, some others joined, like fine data-filtering,
determination of the total uncertainty, tools for report generation,
graphics and further calibration records.

Finally, when it was concluded the development of the version 2.0.0 of
the application ``calibration``, it was clear that a formal package
should be released, separately from the former tool. By doing so, some
of the resources created are now at disposal of the community, under a
3-clause BSD License.

The main path chosen for the development of |app| is that, as functions
and classes created for its use at the laboratory are being adapted to
general cases, and their robustness and performance are considered
proved enough, they will be progressively incorporated to
the ``pvlab`` library. In order to clarify the features and abilities of
the objects created, docstrings of relevant functions or classess
contain examples, which have been verified with the python built-in
package ``doctest``. In addition, there should be a *test_[module]*
for each one, checked by using the *unittest* built-in package.
