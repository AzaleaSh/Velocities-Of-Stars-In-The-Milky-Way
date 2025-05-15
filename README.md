This repository contains a Python script to calculate the radial velocities of several stars based on radio spectral data. The script processes astronomical observation data to identify spectral lines and determines the velocity of the observed stars relative to the observer using the Doppler effect.

Prerequisites
To run this script, you need to have the following Python libraries installed:

* pandas
* numpy
* matplotlib

The script performs the following steps:

* Loads Data: Reads five fixed-width format data files into pandas DataFrames. Each file is expected to contain radio observation data, specifically frequency and flux measurements.
* Defines Expected Frequencies: An array expected_frequencies is defined containing a set of known rest frequencies for expected spectral lines.
* Processes Data (per file): The flux_avg function is called for each loaded DataFrame.
* It first filters out the top and bottom 5% of flux values to reduce noise.
* It calculates the mean and standard deviation of the remaining flux values.
* It identifies potential spectral lines as data points where the flux is greater than the mean plus five times the standard deviation.
*For each identified spectral line frequency, it finds the closest match in the expected_frequencies array.
*Using the identified observed frequency and the closest expected rest frequency, it calculates the radial velocity of the star using the relativistic Doppler formula.
*It prints the list of possible velocities found.
*It calculates and prints the average velocity and its error (standard error of the mean) for the star corresponding to the current data file.
*It indicates whether the star is moving towards or away from the observer based on the sign of the average velocity.
*Iterates through Data: The script loops through the list of loaded DataFrames and a corresponding list of star numbers (1 through 5), calling the flux_avg function for each pair.
