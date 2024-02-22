# Installing the workshop environment

## Overview

This workshop is delivered mainly through a series of [Jupyter notebooks][1]
that allow for interactive Python programming.

To use these, several Python packages must be installed. A full list of these
can be found in [`environment.yml`](environment.yml). 
Should you want to install MDAnalysis under a separate environment, you can find the installation instructions here: https://www.mdanalysis.org/pages/installation_quick_start/.
See below for instructions on how to set up a local copy of the Python environment.

## Installing the Python environment

Due to the complexity of the workshop environment, we strongly recommend the
use of the [Anaconda Python distribution][2]. The instructions provided here
assume the use of [conda][3].

### 1. Creating a workshop environment

To create an environment named `mda_workshop` with all the necessary
Python dependencies:

```bash
conda env create --file=environment.yml
```

See the [conda documentation][4] for more information on how to access and
manage [conda][3] environments.

To then activate this environment:

```bash
conda activate mda_workshop
```

### 2. Activating the Jupyter extensions

The workshop leverages the extended utility of several Jupyter nbextensions.

To install these, the followed should be run **once** (after having activated
the conda environment):

```bash
jupyter contrib nbextension install --user
jupyter nbextension enable splitcell/splitcell
jupyter nbextension enable rubberband/main
jupyter nbextension enable exercise2/main
jupyter nbextension enable autosavetime/main
jupyter nbextension enable collapsible_headings/main
jupyter nbextension enable codefolding/main
jupyter nbextension enable limit_output/main
jupyter nbextension enable toc2/main
```

# Installing Blender and Molecular Nodes

> :warning: **Blender uses its own Python and MDAnalysis installation, so these will live separately to those installed in the earlier parts in this tutorial.**
> 
This is a brief overview of the installation instructions which can be found on the [Molecular Nodes][5] website.

1. Download the latest stable [Blender][6] (Currently 4.0)
2. Download the corresponding latest release of [Molecular Nodes][7] (currently 4.0.9)
3. Install the `molecularnodes_4.0.9.zip` into Blender via the add-ons panel in the preferences.
4. Use the `Install` buttons to install _at least_ `biotite` and `MDAnalysis` into Blender's bundled python.

For more details on these steps, visit the [Molecular Nodes][5] installation page.

## Install BNotebooks for interactive visualization

Assuming you have already installed Blender and MolecularNodes, you can follow these steps to install BNotebooks.

1. Download the corresponding latest release of [BNotebooks][8] (currently 0.0.5)
2. Install the `BNotebooks_0.0.5.zip` into Blender via the add-ons panel in the preferences.
3. Click `install jupyterlab` and DON'T PANIC! An error is likely to occur here. Just restart Blender and open the add-ons panel again. You should see that the jupyterlab extension is installed.
4. Click `Append Kernel` and a jupyter kernel should be installed correctly with the corresponding name.
5. Open a jupyter notebook locally and select the kernel you just installed. A new Blender window should open and you should be able to run the cells in the notebook. (start with `import bpy`)


[1]: https://jupyter-notebook.readthedocs.io/en/stable/
[2]: https://docs.anaconda.com/anaconda/install/
[3]: https://conda.io/projects/conda/en/latest/index.html
[4]: https://docs.conda.io/projects/conda/en/latest/user-guide/getting-started.html?highlight=conda%20activate#managing-environments
[5]: https://bradyajohnston.github.io/MolecularNodes/installation.html
[6]: https://www.blender.org/download/
[7]: https://github.com/BradyAJohnston/MolecularNodes/releases/
[8]: https://github.com/BradyAJohnston/BNotebooks/releases