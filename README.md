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

## Rhino/Grasshopper Geometry Generation Script: 
Generates geometry and writes simulation file.

Filename: GHGenerator.gh

Type: Grasshopper

### Instructions
1. Select save path (preferably a folder)
2. Select desired simulation ID by modifying or adjusting the slider
3. Enable saving to write files to directory

### Default settings:
 
 -Office room 5x5x2.5m 
 
 -Vents and furnitures with rule-based placement
 
 -Saves to FDS file at specified location

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

## Filtering Script

## TODO:

- Results Visualization Script
- Batch Simulation Shell Scripts
- HDF5 Script
