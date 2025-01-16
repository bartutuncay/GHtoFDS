# GHtoFDS
FDS Grasshopper Dataset Generation

### Requirements:
- Rhinoceros 7/Grasshopper
- Python 3.10 or newer

### Python Libraries:
h5py
pandas
fdsreader
matplotlib
PIL
numpy
scipy

## Rhino/Grasshopper Geometry Generation Script: 
Generates geometry and writes simulation file.

Filename: GHGenerator.gh

Type: Grasshopper

### Instructions
1. Select save path (preferably a folder)
2. Select desired simulation ID by modifying or adjusting the slider
3. Enable saving to write files to directory

### Default settings:
 - Office room 5x5x2.5m 
 - Vents and furnitures with rule-based placement
 - Saves to FDS file at specified location
 - Simulation duration: 600 seconds
 - Outputs: Temperature, Velocity (u,v,w, general), Pressure

## Attributes Script:
Helps generate a Pandas dataframe to collect simulation attributes in a single environment.

Filename: Attributes_DF.ipynb

Type: Jupyter Notebook

### Instructions
1. Specify simulation file path
2. Go through cells to generate dataframe and save CSV

### Default settings:
 - Uses simulation save path
 - Saves CSV file

### Output structure:
- Simulation ID (int)
- Vent type (str)
- Ambient temperature (int)
- Floor heating (bool)
- Radiator (bool)
- Supply temp (int)
- Wall temp (float)
- Room dimensions (tuple: x,y,z)
- Furniture locations (array: tuples of x,y,z)
- Radiator location (tuple: x,y,z)
- Supply vent locations (array: tuples of x,y,z)
- Exhaust vent extents (tuple: x,y,z)
- Device locations (array: tuples of x,y,z)
- Occupant locations (array: tuples of x,y,z)
- Supply velocity (float)
- Case type (str: heating, cooling, ventilation)
- Heating system (str: none, floor heating, radiator, forced air)

## Batch Simulation
Single simulations may be performed on a local device from the terminal, by moving to the simulation directory and running: fds simID.fds

For parallelization and higher efficiency, a HPC cluster can be used with the script: Batch.sh

### Instructions
1. Copy simulation files on cluster
2. Modify Batch.sh to contain the correct number of simulations and path
3. Modify parameters if necessary

### Default settings:
The following parameters gave the best results for batches of 500 simulations, your mileage may vary:
- Max. CPU time: 2 hours
- Number of parallel tasks: 10
- Number of nodes: 6
- Number of tasks per node: 2
- Number of CPUs per task: 1

## Filtering and Visualization
Jupyter notebook for parsing through FDS output files.

Filename: Filtering.ipynb

Type: Jupyter Notebook

### Instructions
1. Import libraries
2. Define simulation file paths for processing
3. Obtain heat release rate; options to plot mean squared and absolute error, filter erratic cases
4. Plotting for temperature, velocity quantities aggregated by case attributes
5. Curve fitting for different quantities
6. Calculation tool for device and occupant heat gains

### Default Settings
...


## Writing to Database
...

## Reading the Database
...

## References
- Fire Dynamics Simulator: https://github.com/firemodels/fds
- FDSReader: https://github.com/FireDynamics/fdsreader
