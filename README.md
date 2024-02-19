# MDAnalysis Workshop, February 2024

**NOTE: Materials for this workshop are currently under construction and likely to change - please check again closer to the workshop date.**

## Schedule
*Schedule is subject to change*
| Time | Topic | Instructor |
|-----|-----|-----|
|03:00 - 03:05 UTC | Introduction | |
|03:05 - 04:15 UTC | MDAnalysis Lecture 1 / Tutorial 1 | [Fiona Naughton](https://github.com/fiona-naughton) |
|04:14 - 04:20 UTC | Q&A / Break| |
|04:20 - 05:30 UTC | MDAnalysis Lecture 2 / Tutorial 2 | [Lily Wang](https://github.com/lilyminium) | 
|05:30 - 05:35 UTC | Q&A / Break ||
|05:35 - 06:45 UTC | Molecular Nodes Lecture / Tutorial | [Brady Johnston](https://github.com/BradyAJohnston) |
|06:45 - 06:50 UTC | Final Announcements ||
|06:50 - 07:00 UTC | Final Q&A ||

## Workshop pre-requisites

The workshop assumes that attendees have a working knowledge of MD simulation workflows, [Jupyter notebooks][1], Python (especially the [NumPy library][2]), and the bash shell.


## Google Colab


If for any reason you cannot set up a local environment with all required packages as explained below, you can use Google Colab to run all workshop notebooks directly from your browser, no installation required. 

| Session                 | Materials |
|-------------------------|-----------|
| Lecture 1: MDAnalysis Basics| [![MDA Part 1 Lecture](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/MDAnalysis/MDAnalysisWorkshop-Intro0.5Day/blob/feb24-ws/notebooks/Lecture1_MDAnalysisBasics.ipynb) |
| Tutorial 1: System Manipulation and Atom Selection  | [![MDA Part 1 Tutorial](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/MDAnalysis/MDAnalysisWorkshop-Intro0.5Day/blob/feb24-ws/notebooks/Tutorial1_System_Manipulation.ipynb) |
| Lecture 2: Distance Calculations | [![MDA Part 2 Lecture](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/MDAnalysis/MDAnalysisWorkshop-Intro0.5Day/blob/feb24-ws/notebooks/Lecture2_Distance_calculations.ipynb) |
| Tutorial 2: Distances and Trajectories | [![MDA Part 2 Tutorial](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/MDAnalysis/MDAnalysisWorkshop-Intro0.5Day/blob/feb24-ws/notebooks/Tutorial2_Distances_Trajectories.ipynb) |


## Setting up your Python environment *before the workshop*

<!--The workshop will be in a blended learning environment and hands-on. You will need a working installation of MDAnalysis and related packages including data to analyze in order to participate. The full installation may take up to about 1 GB of space (mostly for data, which you can delete after the workshop).--> 

Instructions for setting up your environment to run this workshop locally
are provided in [`INSTALL.md`](INSTALL.md).

A full list of the required Python packages can be seen inside [`environment.yml`](environment.yml).

As downloading and installing everything will take a little while, ideally you should follow these steps before the workshop starts. If you encounter any issues during installation, we can help!

**Note:** Materials may change between now and the time of the workshop, so while we ask you to install ahead of time, also make sure to `git pull` just prior to the start of the workshop.


## Code of Conduct

All members of the MDAnalysis community and participants in MDAnalysis workshops are expected to abide by the MDAnalysis [Code of Conduct](https://www.mdanalysis.org/pages/conduct/).

## License

Written materials are provided under the [CC-BY-4.0 SA license](LICENSE.md).

The MDAnalysis logo and its derivatives are licensed under the Creative Commons Attribution-NoDerivs 3.0 Unported License.

## Acknowledgements

Please see [`AUTHORS.md`](AUTHORS.md) for a list of contributors to the workshop
materials.

This workshop has been made possible in part by a [grant](https://chanzuckerberg.com/eoss/proposals/mdanalysis-outreach-and-project-manager/) from the Chan Zuckerberg Initiative DAF, an advised fund of Silicon Valley Community Foundation (funder DOI 10.13039/100014989). MDAnalysis also thanks NumFOCUS for its continued support as our fiscal sponsor.

##
[1]: https://jupyter-notebook.readthedocs.io/en/stable/
[2]: https://numpy.org/
