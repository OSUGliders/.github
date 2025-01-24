# Glider Research Group - Oregon State University

The [Glider Research Group](http://gliderfs.coas.oregonstate.edu/gliderweb/) works to understand a diverse range of oceanographic processes, from hypoxia on the US West Coast to mesoscale eddy dynamics in the Western Pacific. We use gliders and a range of other oceanographic tools including moorings, profilers, drifters, and bow chains. We write open-source code to prepare and analyse oceanographic data, and for decision making when in the field. One of our primary goal is to produce standardized, quality-controlled datasets that are ready for scientific analysis and archival. 

## Slocum glider processing

We process Slocum glider data using several tools detailed below. 

#### Binary conversion tools
* [dbd2netcdf](https://github.com/OSUGliders/dbd2netcdf) converts the Slocum binary data format (tbd, dbd, ... etc) into a time series in netCDF format. It can be used on both the decimated real-time and post-recovery data. Written in C by Pat Welch, it is extremely fast and serves the entrypoint for most subsequent processing steps.
* [q2netcdf](https://github.com/OSUGliders/q2netcdf) converts MicroRider q-files into a netCDF format. The q file is a reduced data format transmitted over iridium. The full microstructure data contained in p files are processed using a different tool described in the microstructure section below.

#### Other tools
* [RecoverBy](https://github.com/OSUGliders/RecoverBy) estimates the battery life remaining to help with recovery decisions. 

## Microstructure processing

We use Rockland Scientific Instruments (RSI) VMP250 and MicroRider sensors.

#### 
* [perturb](https://github.com/jessecusack/perturb) is a parallelized MATLAB package built on top of the RSI's ODAS microstructure processing toolbox. It consumes microstructure p files, as well as ancillery data (GPS fixes), and produces complete binned datasets as well as numerous intermediate data products. It has features for assessing data quality and detecting bottom impacts. 
