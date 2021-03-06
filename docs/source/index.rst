.. rritk documentation master file, created by
   sphinx-quickstart on Tue Aug  1 17:41:57 2017.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Welcome to rritk's documentation!
=================================

For now, I'll copy what's in the Github description:

____________________________________________________
# RRI-Toolkit
____________________________________________________
A mini-toolkit for performing various analyses on RRI .h5 files from the 
Radio Receiver Instrument in the ePOP scientific payload of the CASSIOPE satellite.

Started out looking at *conjunctions* of the satellite data files coinciding with 
fields of view of the SuperDARN radars (see conjunctions). Now includes plotting 
tools, analytical tools for estimating various geometric features from transmitter 
to RRI, and some ionospheric parameter modeling.

This is a work-in-progress.


**Install:**
This tool has *not* been made particularly portable yet. A surefire automatic install
process does not exist. However, setting up a virtual environment ( http://docs.python-guide.org/en/latest/dev/virtualenvs/ ) 
and then using "> pip install -r requirements.txt" should cover most of your needs.

The script will create several subdirectories for mounting and saving data:
./data, ./data/output, ./data/remote. It initially (when data_utils.initialize_data 
is called) checks to ensure they are present, and if not, creates them.

In addition, some of the data is retrieved from a server from which 
authentication is done by the user, so unless you have access to it
already, that won't work either. 

**Packages:**
The 'analysis' package contains 'magnet_data' and 'analysis_tools' for performing
estimation, simulation, and analysis.

A package for plots ('plots') will allow a few configurations of plots of 
CASSIOPE ground tracks (including some with SuperDARN FOV's overlaid). Various
parameters that are estimated in the 'analysis' package can be plotted using these
functions.

The 'conjunctions.conjunctions' package contains data which runs through coordinates 
of RRI geographic positions, determines which SuperDARN radars may be relevant,
and summarizes them and the contents of their 'errlog' information files from
that time period. Further study is available using the 'time_align' module.

**Usage:**

*Conjunctions*
If you happen to have a computer with all the correct software and you have
access to the data server, the script can be used by calling it at the 
command line with the desired RRI data file as an additional argument:

If pwd is rritk top directory (or optionally use the -i option to tell Python
to enter interactive mode after running the script):
> python rritk/conjunctions/conjunctions.py ./data/RRI_20160401_072744_033718_lv1_v2.h5

> python -i rritk/conjunctions/conjunctions.py ./data/RRI_20160401_072744_033718_lv1_v2.h5

Reading the documentation and using the functions directly could work too, since it's not super externally usable yet!

*Analysis Tools*
This package is intended to function purely as a library that can be imported.
Directly running 'analysis_tools' as above will result in a variety of automatic tests and 
demonstrations to be run. 

*Plotting*
Library functionality is also intended for this package, with the exception of the 'fig1_plots.py' file,
which can be run on its own (if you have the specified RRI data files) to plot 5 ground tracks near Ottawa
from April 2016.

*Utils*
Importing and using the data_utils package is necessary for use of this package. Use initialize_data()
to ensure a data directory structure is set up and the script is connected to the remote server containing
various data sources.


.. toctree::
   :maxdepth: 2
   :caption: Contents:


Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
