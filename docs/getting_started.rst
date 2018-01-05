.. PopulationSim documentation master file
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Getting Started
===============

This page describes the getting started procedure for PopulationSim which consists of installing and running examples. Users can choose among the following two methods to install PopulationSim

* `Beginner Installation Procedure`_. Download, Unzip, Run!
* `Advanced User Installation Procedure`_. Install from scratch


Beginner Installation Procedure
--------------------------------

1. Download `Anaconda installation ZIP <https://resourcesystemsgroupinc-my.sharepoint.com/personal/binny_paul_rsginc_com/_layouts/15/guestaccess.aspx?docid=1d070faa5aa0948dc9e0d21b40ab837c6&authkey=AVs4vsRQWHldr9eNZaGRBYE&expiration=2018-07-04T01%3A22%3A52.000Z&e=3eaf7253a28f478393af925f8cd7d45c>`_ loaded with all required libraries and PopulationSim package. 

*The Anaconda Python 2.7 and dependent libraries used to prepare this installation folder were accessed on 27th Dec 2017*

2. Unzip and copy the Anaconda2 folder to any location on your computer. 

3. Now proceed to `Run Examples`_


Advanced User Installation Procedure
-------------------------------------
1. If you access the internet from behind a firewall, then you will need to configure your proxy server. To do so, create a .condarc file in your Anaconda installation folder (i.e. ``C:\ProgramData\Anaconda2``), such as:

::

  proxy_servers:
    http: http://proxynew.odot.state.or.us:8080
    https: https://proxynew.odot.state.or.us:8080
  ssl_verify: false

2. Install `Anaconda Python 2.7 <https://www.continuum.io/downloads>`__. 

   **Windows users can skip the remaining steps and run** `SetUpPopulationSim.bat <https://resourcesystemsgroupinc-my.sharepoint.com/personal/binny_paul_rsginc_com/_layouts/15/guestaccess.aspx?docid=1a8ce9c8b1e9347688ccf1f619013df9d&authkey=AUxp6iOeXMFnYM8SrOEv79w&expiration=2018-07-04T01%3A23%3A33.000Z&e=1560c9164b1a4b9da628e807dbd8ca0f>`_ script. The user would need to set the location of the Anaconda installation directory in the batch script (open in edit mode) as shown below:

 ::

   :: USER INPUTS
   :: ---------------------------------------------------------------------
   :: Local Anaconda installation directory
   SET ANACONDA_DIR=E:\path\to\this\directory\Anaconda2
   :: ---------------------------------------------------------------------

 *Please ensure that the user has write permissions to Anaconda installation directory*
 
 **Users who ran the SetUpPopulationSim.bat script can proceed to** `Run Examples`_
	
3. Create and activate an Anaconda environment (basically a Python install just for this project)
  
  * Run ``conda create -n popsim python=2.7``
  * Run ``activate popsim`` #you can re-use the environment on a later date by re-activating it
  
4. If you access the internet from behind a firewall, then you will need to configure your proxy server when downloading packages. For example:

::

  pip install --trusted-host pypi.python.org --proxy=proxynew.odot.state.or.us:8080  activitysim
 
5. Get and install other required libraries, which can be found on the `Python Package Index <https://pypi.python.org/pypi>`__.  Run the following command on the activated conda Python environment: ``pip install <packagename>`` for each package.

  * `toolz <http://toolz.readthedocs.org/en/latest>`__
  * `zbox <https://github.com/jiffyclub/zbox>`__
  * `orca <https://synthicity.github.io/orca>`__ - the application orchestration tool (i.e. the module runner)
  * `openmatrix <https://pypi.python.org/pypi/OpenMatrix>`__ - OMX support
  * `activitysim <https://pypi.python.org/pypi/activitysim>`__ - ActivitySim framework
  * `ortools <https://github.com/google/or-tools>`__ - Google operations research tools solver

6. After setting up Anaconda Python and dependent libraries, run the following command on the activated conda Python environment to install PopulationSim package:

   ``pip install --upgrade https://github.com/RSGInc/populationsim/zipball/master``
 
7. Run ``deactivate`` to deactivate the active conda Python environment

8. Now proceed to `Run Examples`_




Run Examples
------------

	* Before running examples, ensure that Anaconda Python, dependent libraries and PopulationSim package have been installed. In case the fully loaded Anaconda install was downloaded, then it should have been unzipped to an appropriate location on your computer
 
	* Download and unzip the `example set ups <https://resourcesystemsgroupinc-my.sharepoint.com/personal/binny_paul_rsginc_com/_layouts/15/guestaccess.aspx?docid=111557442bbaa49319f43e44aa13e71b2&authkey=ATY9Qg2vIOMGg7QnhTP5-z8&expiration=2018-07-04T01%3A24%3A01.000Z&e=8976518297724d6980780b41edfbd5ce>`_ to the *Project Directory* on your computer

Data from the Corvallis-Albany-Lebanon Modeling (CALM) region in Oregon, USA was used to create the example set ups. `Example_calm`_ set up runs PopulationSim with base configuration. `Example_calm_repop`_ set up runs PopulationSim in the *repop* configuration. More information on configuration can be found in the **Application & Configuration** section

Example_calm
~~~~~~~~~~~~

Follow the steps below to run **example_calm** set up:

  * Open the *RunPopulationSim_base.bat* script from the example_calm folder in edit mode
  * Set the location of the Anaconda installation directory in the batch script as shown below:

  ::

   :: USER INPUTS
   :: ---------------------------------------------------------------------
   :: Local Anaconda installation directory
   SET ANACONDA_DIR=E:\path\to\this\directory\Anaconda2
   :: ---------------------------------------------------------------------  
  
  * Close the *RunPopulationSim_base.bat* script and then double click to launch the run
  * Close the run window by pressing any key. Check the outputs in the *output* folder

Example_calm_repop
~~~~~~~~~~~~~~~~~~

Repop configuration requires outputs from a base run. Therefore, base configuration should be run before running the repop configuration. Follow the steps below to run **example_calm_repop** set up:

  * Copy the **pipeline.h5** file from the example_calm\\output directory to example_calm_repop\\output directory (all PopulationSim files are stored in pipeline.h5 file)
  * Open the *RunPopulationSim_repop.bat* script from the example_calm_repop folder in edit mode
  * Set the location of the Anaconda installation directory in the batch script as shown below:

  ::

   :: USER INPUTS
   :: ---------------------------------------------------------------------
   :: Local Anaconda installation directory
   SET ANACONDA_DIR=E:\path\to\this\directory\Anaconda2
   :: ---------------------------------------------------------------------  
  
  * Close the *RunPopulationSim_repop.bat* script and then double click to launch the run
  * Close the run window by pressing any key. Check the outputs in the *output* folder

