Data Reduction
==============

Roughly speaking, reduction is the process that yields a (static or
dynamic) scattering structure factor from a set of *neutron events*.

In BASIS, a neutron event is described by the time stamp upon emission of
the neutron from the moderator, the time-stamp upon arrival to the detector,
the kinetic energy of the neutron when hitting the detector, and the location
of the detector. With these quantities it is possible to compute the
momentum and energy transfer of the neutron when interacting with the sample.

A set of nice
`primer lectures <https://neutrons.ornl.gov/sites/default/files/intro_to_neutron_scattering.pdf>`_
to neutron scattering.


Reduction algorithms
--------------------

Just two algorithms are needed to reduced elastic and quasielastic neutron
events.

BASISDifraction
~~~~~~~~~~~~~~~

Elastic detector tubes are arrayed along the equatorial line of the walls.


BASISReduction
~~~~~~~~~~~~~~

Inelastic detector tubes are located above and below the elastic detector
tubes, and are arranged into four banks of detectors. Each bank contains XXX
tubes and each tube contains XXX detectors.

/picture here denoting 111 and 311 detectors/

Three banks contain Silicon-111 detectos and only one contains Silicon-311
detectors.


Creating a Custom Mask File
---------------------------


