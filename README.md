# Scenarios for "Spatial Models and Masks in Indoor Analysis for the Spread of COVID-19"

Simulates a number of different scenarios described in the paper titled "Spatial Models and Masks in Indoor Analysis for the Spread of COVID-19". All the scenarios have already been run and the results have been converted into a format that is easier to use with the Web Viewer. The files in the Visualization folder are organized such that you can upload the log file along with both json files to the Web Viewer to visualize the results.

## Installation

1. Make sure you have cadmium installed before proceding, see the [User Manual](http://www.sce.carleton.ca/courses/sysc-5104/lib/exe/fetch.php?media=cadmium.pdf) for more details.
2. Navigate to **CADMIUM/** directory and run `git clone https://github.com/SimulationEverywhere/Cell-DEVS-Cadmium-Simulation-Environment`
3. Navigate to **CADMIUM/Cell-DEVS-Cadmium-Simulation-EnvironmentRun/** and run `git submodule update --init --recursive`
4. Copy the folder this README file is in (Cell-DEVS-Mask-Effects) to **CADMIUM/Cell-DEVS-Cadmium-Simulation-EnvironmentRun/Cadmium-Cell-DEVS-Models/**
5. Open a terminal or bash prompt in the copied folder and execute the command 'cmake ./'
6. If successful, there will be a makefile in the current folder, now execute the command 'make'
7. If successful, this will create the executable called 'vp'

## Running a Scenario

All the scenarios are stored as JSON files in the Configs folder, to run the Batch1 Cotton one with a run time of 2000 for example, you can execute the command './vp Configs/Batch1/restaurant-cotton.json 2000'

The results will be saved in the 'Results' folder. Running it again will overwrite the results if they are not moved.

## Visualizing a Scenario

To visualize a supplied scenario, upload the log file along with both json files in the folder to the web viewer and load the simulation.

For example for the Batch 1 Cotton scenario, upload these files:
- '/Visualization/Batch1/COTTON/messages.log'
- '/Visualization/Batch1/COTTON/options.json'
- '/Visualization/Batch1/COTTON/structure.json'

The preffered and tested web viewer can be found at http://ec2-3-235-245-192.compute-1.amazonaws.com:8080/devs-viewer/app-simple/

## Models

All scenarios are also listed in the .xml file.

### Batch1

- restaurant-no_mask.json: All not wearing any mask
- restaurant-cotton.json: All wearing cotton masks
- restaurant-surgical.json: All wearing surgical masks
- restaurant-N95.json: All wearing unfitted N95 masks
- restaurant-N95_fit.json: All wearing fitted N95 masks

### Batch2

#### source-no_mask

- restaurant-no_mask-cotton: emitter not wearing mask, receivers wearing cotton masks
- restaurant-no_mask-surgical: emitter not wearing mask, receivers wearing surgical masks
- restaurant-no_mask-N95: emitter not wearing mask, receivers wearing unfitted N95 masks
- restaurant-no_mask-N95_fit: emitter not wearing mask, receivers wearing fitted N95 masks

#### source-cotton

- restaurant-cotton-no_mask: emitter wearing cotton mask, receivers not wearing masks
- restaurant-cotton-surgical: emitter wearing cotton mask, receivers wearing surgical masks
- restaurant-cotton-N95: emitter wearing cotton mask, receivers wearing unfitted N95 masks
- restaurant-cotton-N95_fit: emitter wearing cotton mask, receivers wearing fitted N95 masks

#### source-surgical

- restaurant-surgical-no_mask: emitter wearing surgical mask, receivers not wearing masks
- restaurant-surgical-cotton: emitter wearing surgical mask, receivers wearing cotton masks
- restaurant-surgical-N95: emitter wearing surgical mask, receivers wearing unfitted N95 masks
- restaurant-surgical-N95_fit: emitter wearing surgical mask, receivers wearing fitted N95 masks
