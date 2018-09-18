Welcome to the WWU Mastcam Spectral Plotter!

To use the plotter, download the file corresponding to your operating system, and run the executable file by clicking on it on Windows, or on MacOS:
navigate to directory of executable in terminal and run the command ./MSP

Basic functionality is given below.


THE MENU
-----------------------------------------------------------
File -> Import: Updates data from what is currently uploaded to the WWU Mastcam database. It is stored in a file called 'spectra_list.p' in the same directory as the executable. You must be connected to the Ricedata server in order for this functionality to work. You don't need to update your spectra very often, just when you want to add the newest data. Most people will not have access to the server, and so should download the most up to date 'spectra_list.p' from the Github.

File -> Plot: Press when you want to actually plot the data. Opens a plot window.

File -> Export CSV: Exports a csv containing data from your input below.


Options -> R* Correction: Have this option checked if you wish to have the data R* corrected when it plots. An R* correction divides reflectance by the cosine of the emission angle. Defaults to being on.

Options -> Display geologic units in elevation plot: If the Y axis is selected to be elevation, this option overlays lines indicating boundaries between geologic units and members.

Options -> Normalization point: From this submenu, selected the filter you would like to normalize L and R eyes at. Defaults to 639. NOTE: If an observation does not have data from each eye, or from each overlapping filter, it cannot be normalized, and will not be plotted.

Options -> Error Bar Options: Display which type of error bars will be displayed. Error bars are off by default. Representative error bars are an average of all error bars for plotted data points.

Options -> Color Options: Choose what type of color will be applied
	Black: All data is black
	Color from elevation: Color is applied as a gradient representing elevation of observation.
	Color from feature type: Color is determined by feature type. Color coding is as follows:

	    red: Undisturbed Soil
            light green: Dust-Cleared Outcrop
            light blue: Dusty Outcrop
            dark blue: Dusty Outcrop
            teal: Dusty Outcrop
            light cyan: Nodule-rich Outcrop
            dark green: Broken Rock
            light purple: Drill Tailings
            pink: Other
            sienna: Other
            bright red: Undisturbed Soil
            yellow: Other
            goldenrod: Veins
            dark red: Disturbed Soil
            dark purple: Dump Piles


PLOTTING
----------------------------------------------------------
Select X and Y conditions from the corresponding menus.

Options are:
	Reflectance: Raw reflectance from a given filter.
	Band Depth: Calculates band depth given a left shoulder point (l), a middle point (m), and a right shoulder point (r). Equation used is (((ly - ry) / (lx - rx) * (mx - lx)) + ly - my).
	Slope: Calculates slope between two points (l and r). Equation used is ((ly - ry) / (lx - rx)).
	Ratio: Calculate reflectance ration between two points (n and d). Equation used is (ny / dy).
	Sol: Integer value of the sol the observation was taken on
	Elevation: Elevation of target.
	LTST: Local True Standard Time at time of observation.
	Tau: Tau value observed at sol closest to sol of Mastcam observation. Ie, closest approximation to tau value at time of observation.

The conditions menu at the bottom is used to place restrictions or highlights on plotted data. For example, you can use it to only plot data above a give elevation, or in a certain tau range, while highlighting all dusty outcrops. Select the condition you wish to add and click 'add' to add it as a restriction, only plotting observations that meet the restriction. By pressing highlight, you can can highlight any data point that meets the given condition.
Underscores are used to indicate ranges. Example user input conditions are seen below. For sol range only, you can use commas to seperate individual sols and ranges. Use commas, not underscores, for Mcam IDs.
As of now, only one condition of each type can be applied. For example, you can restrict the sol range and highlight sols within that range, but you can't have two seperate tau restrictions.

---Examples---
Sol Range: 1,14,15,100_500,750_1000,17
LTST Range: 10:13:00_15:24:15
Tau Range: .4_1
Elevation Range: -4300_-4250
Mcam IDs: 03101,3121,3505

PLOT VIEW
---------------------------------------------------------
When plot is pressed, a plot window will appear a short time later.

Save Plot: This command saves the entire plot as a png or jpg.

Identify point: Click near a data point to show its origin. Be wary, multiple data points may be plotted on top of one another. Use the next tool to ensure you are not accidently showing the data from a different point.

Resize plot: Click two points to resize the plot, with the two points as the opposite corners of the new plot. The order in which the points are clicked does not matter. As of now, the plot cannot be set back to its original size, just replot the data. Use this tool to get a better glimpse at tightly packed data, or make sure you are clicking the correct point to identify.


BUGS
---------------------------------------------------------
There will be bugs. If you encounter one, please let me know about it with as much detail as possible. Specifically, let me know what operating system you are on and what I can do to reproduce the bug. Email me at starrm@wwu.edu.