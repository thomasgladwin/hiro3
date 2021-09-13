Hiro3 (please cite using Gladwin TE, Vink M, Mars RB (2016). A landscape-based cluster analysis using recursive search instead of a threshold parameter. MethodsX, doi:10.1016/j.mex.2020.100947) is a visualization program for .img and .nii format (f)MRI data. The toolbox evolved over time during one of my post-doc periods, accruing functionality as needed. Short tutorial: load an anatomy and a functional layer via the File menu. Click on the transversal, sagittal and coronal slice views to navigate. Clicking provides a best-guess anatomical label and Brodmann number, both of which can be completely wrong if there's no label nearby. These labels are also exported along with other information about centres of activation.

As always, be careful about whether left and right might be swapped in the data!

Current functionality:

- The program is also an interface to the landscape-based cluster definition method (Gladwin, Vink & Mars, 2016) of primary interest for cluster analysis; the "blobbify" function for separating and labelling regions of activity surrounding peaks. The function combines regions if one is surrounded by another by a specified proportion of edge-voxels (0.25 by default). Finally, within-subject whole-brain corrected cluster analysis for t-tests is available via the GUI.

- The function hiro3_do_PPI_subject creates a beta-map for a psychophysiological interaction (PPI) regressor for a single subject, given the expected inputs (onsets file, cell array of functional scans, correctly resliced {0, 1} mask for creating the physiological vector, etc) as specified in the function's help. The function uses basic SPM commands but avoids things like VOI structures - the function just goes from the preprocessed functional scans etc to beta maps for second level analyses.

- Convert maps to masks. Adding a mask-map as a second activation layer allows the second layer to be used to mask the first layer: Voxels with zero values in the mask are set to zero in the activation layer at layer 1.
  
- Interactive animation of a sequence of volumes, under Display, Animation movie. The interface uses modes that I hope work more intuitively than it might seem explained in text... Time mode: Click on the time-course subplots at the bottom of the figure to start versus stop (at the clicked position) running through volumes. Space mode depends on whether the animation is running or stopped. While running, clicking on the scan images at the top of the figure toggles between viewing a specific slice and showing the maximum, variance or maximum absolute difference from the previous volume over a given dimension, or a slice. While stopped, clicking on the brain images starts and stops looping over slices to be shown while running over time in slice mode. If running is started while slices are looping, the program will loop through slices nested in volumes.

- Glass brain (press G). Distance from the viewer's point of viewer is indicated by fading.

- Multiple overlays can be plotted, each with an independently chosen color scheme and transparency. See the Display menu for the color scheme and transparency dialog.

- Cutoff values for functional overlays can be adjusted without reloading data (press C or use the Data menu). When multiple activation layers are loaded, independent cut-offs can be entered, separated by spaces, in the cut-off dialog. This is especially useful when combining activation data (use a statistical cut-off, e.g. 4) with masked of label-map data (set cut-off to zero).

- Saves figures as 600 dpi tiffs.

- Pressing space toggles between navigation and replace-value mode. Pressing R (or the menu item in the Data menu) allows users to change the value applied to clicked voxels in replace mode. 

Requires SPM to work. 
