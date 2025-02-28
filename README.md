# Storm Surge Parametric Inputs
This repository provides code for creating and filtering parametric model inputs derived from the NHC Hurricane Archive. The filtering process uses overlapping data from the NOAA HRRR model. Additionally, the repository includes code to extract subset domains from the NOAA HRRR dataset based on extracted NHC hurricane tracks (by date, latitude, and longitude).

![Sample HRRR subset domain overlaid on a hurricane track](https://github.com/JoeBeyrer/storm-surge-parametric-inputs/blob/main/assets/hrrr_subset_track.png?raw=true)

## Run Order
1. Run each cell in `filterData.ipynb` to filter the NHC Hurricane Archive data
2. Run `inpData.ipynb` cells to generate a dictionary-based dataset for the filtered data
3. Run `herbieLoading.ipynb` to load HRRR data and create a custom subset for overlapping NHC Hurricane Archive Data

## Repository Structure
- `filterData.ipynb`: Loads and filters NHC Hurricane Archive data to ensure compatibility with HRRR data
- `inpData.ipynb`: Demonstrates various dataset options using dictionary formats to effectively capture time series data
- `herbieLoading.ipynb`: Uses the Herbie tool to load HRRR data and create subsets corresponding to each hurricane track
- `allNHCData.ipynb`: Creates a dataset from all available NHC Hurricane Archive data for data quality analysis
- `loadHRRR.ipynb`: Provides an alternative HRRR loading method via AWS CLI. This method is included for completeness but is less convenient for our use case
- `data`: Directory used to store all data files created and queried for dataset creation and analysis
- `assets`: Contains all assets reference assets

## Requirements
It is recommended to run the following commands in order (in a conda environment) to ensure the underlying C libraries are installed:
1. `conda install -c conda-forge geos proj eccodes cartopy`
2. `pip install -r requirements.txt`

Dependencies can be found in `requirements.txt`:
- pandas
- numpy
- herbie-data
- xarray
- cfgrib
- eccodes
- matplotlib
- cartopy

All code was executed in a conda environment. `pip` requirements can be used with conda > 4.6.0. 
