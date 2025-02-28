# Storm Surge Parametric Inputs

## Run Order
1. Run each cell in `filterData.ipynb` to filter the NHC Hurricane Archive data
2. Run `inpData.ipynb` cells to generate a dictionary-based dataset for the filtered data
3. Run `herbieLoading.ipynb` to load HRRR data and create a custom subset for overlapping NHC Hurricane Archive Data

## File Structure
- `filterData.ipynb`: Loads and filters NHC Hurricane Archive data to ensure compatibility with HRRR data
- `inpData.ipynb`: Demonstrates various dataset options using dictionary formats to effectively capture time series data
- `herbieLoading.ipynb`: Uses the Herbie tool to load HRRR data and create subsets corresponding to each hurricane track
- `loadHRRR.ipynb`: Provides an alternative HRRR loading method via AWS CLI. This method is included for completeness but is less convenient for our use case

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
