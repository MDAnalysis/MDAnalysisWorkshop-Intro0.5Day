---
title: Molecular Dynamics
author: Brady Johnston
bibliography: references.bib
---

# Starting Blender

If you have successfully installed Molecular Nodes, then you should see `Molecular Nodes` as a new starting template when opening Blender.
You can still use Molecular Nodes without starting as a template, but the UI will be slightly different to start with.
When starting with or without the template, you can customise the UI and starting scene to your liking - and even create your own templates.
Included with Molecular Nodes is a template which includes a number of quality-of-life improvements for using Molecular Nodes.

If you do not see this, then please follow the [installation instructions](https://bradyajohnston.github.io/MolecularNodes/installation.html) in the documentation.

![Screenshot of Blender's interface when launching](imgs/splash_screen.png)

# The 'Molecular Nodes' Interface

Blender can have a very overwhelming interface.
The Molecular Nodes template starts with 3 main areas shown - the 3D viewport where the 3D view and rendered view are shown, the Geometry Nodes - where you combine different nodes to style and animate your structure, and the Shader Nodes, where you can quickly adjust the look of the materials applied to your structure.

The other areas are the `Outliner` which shows all of the objects in your 3D scene, the `Properties` where you can adjust all of the scene, render, world, material and other properties, and the `Timeline`, which shows the current and surrounding frames if there is an animation to play back.

![Screenshot of Blender's Interface](imgs/workspaces.png)

> Where you mouse is currently hovering over, determines the actions that are triggered by keyboard shortcuts.
> Be sure to move the mouse to the area you want to interact with before using keyboard shortcuts.

You can resize and change the arrangement of the windows by hovering your mouse over the edges of the windows.
You can create new windows by dragging out of the corners of the windows, or combine windows by dragging the corner of one window into another.

> For a more general introduction to Blender, please see the [Blender's Interface](https://bradyajohnston.github.io/MolecularNodes/tutorials/00_interface.html)

## MD Trajectory Panel

To create an animation of the structure opening, we will import one of the example datasets that we have been working with in the previous jupyter notebooks.

The data should already be downloaded onto your computer, found in your home folder under `~/MDAnalysis_data/`.
You can check the path of the files by running this command in one of your notebooks.

``` python
# pip install MDAnalysisData
from MDAnalysisData import datasets
data.fetch_adk_transitions_DIMS()
```

To import trajectories, change the import method in the Molecular Nodes panel to the `MD` import method.

1.  Change the import method from PDB to MD
2.  Select the topology and trajectory files.

Optionally change import settings for style filtering and the addition of extra selections.
Check the documentation for more details on these potential options.

![](imgs/molecular_nodes_panel.png)

### Import Options

Before importing, we can change some of the import settings to be applied on import.
More detail on each option is further in this tutorial, but the short descriptions:

-   `Style` Tick box whether to set up nodes to apply a style, or just import the data. If enabled, a default style to be applied on import is selected. This can be changed easily after import.
-   `Import Filter` a MDAnalysis [selection string](https://userguide.mdanalysis.org/stable/selections.html) to filter the topology when importing. Default is to import everything, but you can input strings such as 'protein' to only import the protein component.
-   `In Memory` Whether to load the selected frames (from `start` to `stop`, incrementing by `step`) into memory and discard the MDAnalysis session when importing. Default is false and streams the trajectory from disk.
-   `Custom Selections` Users can create multiple custom selections that appear as boolean attributes on the imported trajectory. Useful for creating groups using MDAnalysis [selection strings](https://userguide.mdanalysis.org/stable/selections.html) to then utilise inside of the created node tree.

## Import the Trajectory

Click `Load` to import the selected trajectory with the chosen options.
The model will appear in the scene, and once you change frame in the scene, it will update the frame displayed in the viewport.

https://github.com/BradyAJohnston/MDAnalysisWorkshop-Intro0.5Day/assets/36021261/e7b58652-a83c-4bd5-bd7d-5b110adb79b7

### Changing Style

You can change the style by altering the `Style` nodes that are use inside of the node tree.

Inside of Blender, the atoms exist as a 3D mesh. Atoms are individual vertices and bonds between atoms are edges between those vertices. On top of these 'Atoms', we apply a `Geometry Nodes` modifier, which takes in the atomic data from the left, process it through a series of nodes, and the output goes out to the right.

In the initial node setup, Molecular Nodes has added some starting nodes. The first assigns colors to the atoms, based on their assigned element. The second node creates a `Sphere` style, which instances a sphere for each atom in the structure.

The data flows through the node graph from left to right - like water flowing through pipes. We can alter how the data is processed, by changing the inputs on the nodes themselves, which results in changes of the final created geometry.

In the example below, if we remove the style node, we can see that no style is being applied and thus the underlying atoms and bonds are visible as the only processing of the atoms that is occurring is to assign them colors.

https://github.com/BradyAJohnston/MDAnalysisWorkshop-Intro0.5Day/assets/36021261/1b0e1273-9bf2-44c6-95a7-9edf933807b8

> There is not time to go in depth in this tutorial on how node graphs work - please see the [documentation](https://bradyajohnston.github.io/MolecularNodes) for more details and tutorials.

#### Selections

Most nodes will take an optional `Selection` input. This allows you to apply an animation or a style to specific subset of atoms within the structure. 

To access the selections, use the add menu (<kbd>Shift</kbd> + <kbd>A</kbd>) and use `Molecular Nodes` -> `Selections`. We will add the `Element` selection node.


### Subframes

By default, each frame on the timeline matches directly with the frames in the loaded trajectory.

You can add `subframes` which then tell Blender to add additional frames in between, which linearly interpolate between positions.
This can slow down the animation and sometimes make it easier to view.
The subframes for the trajectory can be adjusted in the `Object` section of the Molecular Nodes panel.

The `Frame` number in Blender no longer directly matches the frame displayed from the trajectory, with the trajectory playing back 'slower' than previously.

![](imgs/subframes.png)

### Trasnforming Objects

You can move objects around the scene with the transform keys. This includes imported structures and trajectories. 
You can select objects with a left click of the mouse <kbd>LMB</kbd>, and move them around by *Grabbing* them with the <kbd>G</kbd> key.

The main actions that you use the 3D Viewport for are:

-   <kbd>G</kbd> - **Grabbing:** Moving an object around in 3D space.

-   <kbd>S</kbd> - **Scaling:** Changing the relative size of an object.

-   <kbd>R</kbd> - **Rotating:** Rotating the object in 3D space.

#### Locking to an Axis

When transforming by grabbing, rotating or scaling, you can lock the transformation to a particular axis. Click <kbd>X</kbd> / <kbd>Y</kbd> / <kbd>Z</kbd> after starting the transformation to lock it to those axes, or <kbd>Shift</kbd> + <kbd>X</kbd> / <kbd>Y</kbd> / <kbd>Z</kbd> to lock the transformation to be *perpendicular* to that axis.

https://github.com/BradyAJohnston/MDAnalysisWorkshop-Intro0.5Day/assets/36021261/4ece00a9-d992-48d5-b4ea-bb99d57ced5c

## Streaming vs In Memory

### Streaming

The default option will associate an `MDAnlaysis` session with the read topology file.
This will stream the topology from disk, as the frame in the scene inside of Blender changes.
If the original topology or trajectory files are moved, this will break the connection to the data.
This is the most performant option, but will potentially break if changing computers.

Below is an example of importing a trajectory, by streaming the frames.
As the frame changes in the scene, the loaded frame is updated on the imported protein, based on the created MDAnalysis session.
Interpolation between frames is currently not supported with this import method.

The MDAnalysis session will be saved when the `.blend` file is saved, and should be restored when the `.blend` file is reopened.

![](https://imgur.com/nACvzzd.mp4)

### In Memory

The `In Memory` option will load all frames of the trajectory in to memory, and store them as objects inside of the `MN_data` collection in the scene.
This will ensure that all of the associated data is stored inside of the `.blend` file for portability, but will come at the cost of performance for very large trajectories.
It also breaks the connection to the underlying `MDAnalysis` session, which limits the ability to further tweak the trajectory after import.

If `In Memory` is selected, the frames are imported as individual objects and stored in a `MN_data` collection.
The interpolation between frames is then handled by nodes inside of Geometry Nodes, which aren't necessarily linked to the scene frame.

This will create a larger `.blend` file and can lead to some performance drops with large trajectories, but ensures all of the data is kept within the saved file, and can enable further creative control through Geometry Nodes.

All connection to the underlying MDAnalysis session is lost on import, and the selections and trajectory cannot changed.
To make changes you must reimport the trajectory.

![](https://imgur.com/ZoTfmvl.mp4)



### Rendering an Image

Blender will not render an image of what you are currently seeing like most molecular software you are used to. Blender will render an image based on what the `Camera` is currently seeing. This may seem frustrating at first - but will make more sense the more you use the software and becomes far more intuitive than other methods.

To preview what the camera sees, we can click the `Camera` icon in the 3D viewport. The slightly darkened outline shows what the camera is seeing, and if `Depth of Field` is being used, you will see what is in focus and out of focus.

You can then render an image by clicking `Render` -> `Render Image`, or use the keyboard shortcut <kbd>F12</kbd>.

https://github.com/BradyAJohnston/MDAnalysisWorkshop-Intro0.5Day/assets/36021261/f1942978-d99a-4486-abc1-6b59a6ca1e40

The time it takes for the render to complete will depend a lot on how you have set up the scene, and more importantly the kind of hardware that your computer has. This is unfortunately a limiting step for many. If you have access to external computing resources such as a HPC cluster however - you can set up a scene on your local laptop, and when you are ready to render, render the image or the animation via the command line on a compute cluster.

#### Render Engine and Render Settings

Until now we have been using the `Cycles` render engine. This is a _physically based_ ray-traced rendering engine. It is very computationally intensive, but produces very beautiful renders thanks to its excellent lighting calculations. Blender also includes a second rendering engine that is designed to be faster called `EEVEE`. `EEVEE` is much more like a render engine in a video game or in more traditional molecular visualisation software. We won't go into specifics, but `EEVEE` approximates many things and doesn't use ray tracing to be much faster. It can take some more tweaking and adjustments to get something looking 'nice', but `EEVEE` is an excellent render engine and importantly renders much _much_ faster than cycles.

> Only the `Style Spheres` might not show up in the `EEVEE` engine. There is a tick-box to display it in `EEVEE` as well as `Cycles` by instancing icospheres instead of using perfectly spherical point clouds.

https://github.com/BradyAJohnston/MDAnalysisWorkshop-Intro0.5Day/assets/36021261/239dc5f2-229e-41cf-bb06-0f279cd6236f

To change the rendering engine, you can change it in the `Render Properties` tab, or in the `Scene` tab of Molecular Nodes. In the render properties you can also change the resolution of the render, as well as the number of samples if using the `Cycles render engine.

![Quick access to common render settings in the Molecular Nodes 'Scene' tab](imgs/mn_render_settings.png)



### Rendering the Animation

For the final we can adjust the start and end frames for the timeline to display the trajectory, adding a single subframe to slow things down slightly, and combining two different styles to get the ribbon backbone, and the side chains to be ball and stick.

We can change some final settings of the style, do a test `Render Image`, change the export settings for where the frames of the animation are going to be saved, then we can click `Render Animation` to render all of the frames of the animation.

![](https://imgur.com/IBKUQSr.mp4)
