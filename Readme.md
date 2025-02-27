# ttemtoolbox
A tool box to use for post processing of ttem files generated by Aarhus workbench 

## Install 

```
pip install ttemtoolbox
```
## Quick Start 
Run `ttemtoolbox --get_config <PATH>` to generate the program [configuration](https://github.com/jldz9/ttemtoolbox/blob/master/src/ttemtoolbox/defaults/CONFIG) file 
The configuration file is a one-step for all in this program. You can check the configuration file for more details.
To run the entire process, simply use `ttemtoolbox -c <PATH>` where `<PATH>` is the path to your configuration file. 
This will create a directory tree under output folder specified in configuration file. 
```
output\
  --deliver\ # folder storage all final products from the process
  --temp\ # folder storage all temporary products from the process
    --gamma_temp\
    --ttem_temp\
    --water_temp\
    --well_temp\
```
## CLI usage 
### Main parser
```
ttemtoolbox
options:
  -h, --help            show this help message and exit
  -c PATH, --config_path PATH
                        Run entire ttem rock physics tranform process
  --get_config          Generate default config file
  -f, --force_clean     To force remove all files for new program
  --example_data        To download example data
  -v, --version         show program's version number and exit
```
### ttem sub-parser
```
ttemtoolbox ttem <PATH>
positional arguments:
  PATH                  Path to config file

options:
  -h, --help            show this help message and exit
  --doi_path PATH       Path to doi file
  --layer_exclude int(s) [int(s) ...]
                        Specify exclude layers when processing ttem data, this can also be done in config file
  --line_exclude int(s) [int(s) ...]
                        Specify exclude lines when processing ttem data, this can also be done in config file
  --ID_exclude int(s) [int(s) ...]
                        Specify exclude ID when processing ttem data, this can also be done in config file
  --resample int        Specify resample factor when processing ttem data, this can also be done in config file
  --reproject str       Reproject ttemdata to a new crs, e.g: EPSG:4326
  --unit str            Use "meter" or "feet", default is meter
```
### lithology sub-parser
```
ttemtoolbox lithology <PATH>
positional arguments:
  PATH             Path to config file

options:
  -h, --help       show this help message and exit
  --reproject str  Reproject welllog data to a new crs
  --resample int   Resample welllog data
  --unit str       "meter" or "feet", default is meter
```
### water sub-parser
```
ttemtoolbox water <PATH>
positional arguments:
  PATH                  Path to config file

options:
  -h, --help            show this help message and exit
  -w str[s], --well_no str[s]
                        Download specific well number
```
### ttem-lithology connect sub-parser
```
ttemtoolbox connect <PATH>
positional arguments:
  PATH        Path to config file

options:
  -h, --help  show this help message and exit
```
## Python usage

Check [API document](https://jldz9.github.io/ttemtoolbox/)




