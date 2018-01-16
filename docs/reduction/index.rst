Data Reduction
==============


.. contents:: :local:


Roughly speaking, reduction is the process that yields a (static or
dynamic) scattering structure factor from a set of *neutron events*.

In BASIS, a neutron event is described by the time stamp upon emission of
the neutron from the moderator, the time-stamp upon arrival to the detector,
the kinetic energy of the neutron when hitting the detector, and the location
of the detector. With these quantities it is possible to compute the
momentum and energy transfer of the neutron when interacting with the sample.

A set of useful
`primer lectures <https://neutrons.ornl.gov/sites/default/files/intro_to_neutron_scattering.pdf>`_
to neutron scattering.


Reduction algorithms
--------------------

Just two algorithms are needed to reduced elastic and quasielastic neutron
events.

BASISDiffraction
~~~~~~~~~~~~~~~~
- Problems, questions? Check the FAQ at :ref:`FAQ/index:BASISDiffraction`

Elastic detector tubes are arrayed along the equatorial line of the walls.

.. image:: ../images/reduction/diff_tubes.png
   :scale: 40 %

.. image:: ../images/reduction/diff_tubes_2.png
   :scale: 15 %

Algorithm
`BASISDiffraction <http://docs.mantidproject.org/nightly/algorithms/BASISDiffraction-v1.html>`_
creates a diffraction pattern from a set of runs implementing a rotational
scan of the sample around the vertical axis. Please go to the link to read
how to run this algorithm, as well as for a hands-on example.

To have a feeling of the algorithm, copy the example in the documentation and
run it in the python window of MantidPlot. For the real deal (your sample),
you will need the vanadium run numbers and the background run number of
relevance to your sample. Ask your instrument scientist for this information.

.. code-block:: python

    from mantid.simpleapi import BASISDiffraction
    BASISDiffraction(RunNumbers='74799-74869',  # Here substitute with your runs
                    OutputWorkspace='peaky',
                    VanadiumRuns='64642-64643', # Ask instrument scientist for Vanadium runs
                    BackgroundRun='75527',  # Ask instrument scientist for the background run
                    SampleOrientation=True,
                    PsiAngleLog='SE50Rot',
                    PsiOffset=-27.0,
                    LatticeSizes=[10.71, 10.71, 10.71],
                    LatticeAngles=[90.0, 90.0, 90.0],
                    VectorU=[1, 1, 0],
                    VectorV=[0, 0, 1],
                    Uproj=[1, 1, 0],
                    Vproj=[0, 0, 1],
                    Wproj=[1, -1, 0],
                    Nbins=400)


BASISReduction
~~~~~~~~~~~~~~
- Problems, questions? Check the FAQ at :ref:`FAQ/index:BASISReduction`

Inelastic detector tubes are located above and below the elastic detector
tubes, and are arranged into four banks of detectors. Each bank contains XXX
tubes and each tube contains XXX detectors.

/picture here denoting 111 and 311 detectors/

Three banks contain Silicon-111 detectos and only one contains Silicon-311
detectors.


Creating a Custom Mask File
---------------------------


