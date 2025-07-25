# MDAnalysisWorkshop2023

Materials for the October 25, 2023 MDAnalysis workshop.

## Schedule
Moderator: [Jenna Swarthout Goddard](https://github.com/jennaswa)

| Time | Topic | Instructor |
|-----|-----|-----|
|15:00 - 15:30 UTC | Installation troubleshooting | [Ian Kenney](https://github.com/ianmkenney) | 
|15:30 - 16:30 UTC | Lecture 1 + Tutorial 1 | [Micaela Matta](https://github.com/micaela-matta) |
|16:30 - 16:45 UTC | Q&A / Break||
|16:45 - 17:45 UTC | Lecture 2 + Tutorial 2 | [Richard Gowers](https://github.com/richardjgowers) | 
|17:45 - 18:00 UTC |Q&A / Break ||
|18:00 - 18:30 UTC |Final Q&A | [Fiona Naughton](https://github.com/fiona-naughton) |

## Workshop pre-requisites

The workshop assumes that attendees have a working knowledge of MD simulation workflows, [Jupyter notebooks][1], Python (especially the [NumPy library][2]), and the bash shell.


## Google Colab


If for any reason you cannot set up a local environment with all required packages as explained below, you can use Google Colab to run all workshop notebooks directly from your browser, no installation required. 

| Session                 | Materials |
|-------------------------|-----------|
| Lecture 1: MDAnalysis Basics| [![MDA Part 1 Lecture](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/MDAnalysis/MDAnalysisWorkshop2023/blob/oct23-ws/notebooks/Lecture1_MDAnalysisBasics.ipynb) |
| Tutorial 1: System Manipulation and Atom Selection  | [![MDA Part 1 Tutorial](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/MDAnalysis/MDAnalysisWorkshop2023/blob/oct23-ws/notebooks/Tutorial1_System_Manipulation.ipynb) |
| Lecture 2: Distance Calculations | [![MDA Part 2 Lecture](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/MDAnalysis/MDAnalysisWorkshop2023/blob/oct23-ws/notebooks/Lecture2_Distance_calculations.ipynb) |
| Tutorial 2: Distances and Trajectories | [![MDA Part 2 Tutorial](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/MDAnalysis/MDAnalysisWorkshop2023/blob/oct23-ws/notebooks/Tutorial2_Distances_Trajectories.ipynb) |


## Setting up your Python environment *before the workshop*

<!--The workshop will be in a blended learning environment and hands-on. You will need a working installation of MDAnalysis and related packages including data to analyze in order to participate. The full installation may take up to about 1 GB of space (mostly for data, which you can delete after the workshop).--> 

Instructions for setting up your environment to run this workshop locally
are provided in [`INSTALL.md`](INSTALL.md).

A full list of the required Python packages can be seen inside [`environment.yml`](environment.yml).

As downloading and installing everything will take a little while, ideally you should follow these steps before the workshop starts. If you encounter any issues during installation, we can help!


## Code of Conduct

All members of the MDAnalysis community and participants in MDAnalysis workshops are expected to abide by the MDAnalysis [Code of Conduct](https://www.mdanalysis.org/conduct/).

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
