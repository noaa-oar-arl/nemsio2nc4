# NEMSIO2NC4
The first utility created was the nemsio2nc4.py script. This is a command-line script that converts the nemsio data output by the FV3 system to netcdf4 files using a combination of mkgfsnemsioctl found within the fv3 workflow and the climate data operators (cdo). This tool is available on github at https://github.com/bbakernoaa/nemsio2nc4

```
nemsio2nc4.py --help
usage: nemsio2nc4.py [-h] -f FILES [-n NPROCS] [-v]

convert nemsio file to netCDF4 file

optional arguments:
  -h, --help            show this help message and exit
  -f FILES, --files FILES
                        input nemsio file name (default: None)
  -n NPROCS, --nprocs NPROCS
                        Number of Processors (default: 2)
  -v, --verbose         print debugging information (default: False)
  ```
  
### Example Usage
If you want to convert a single nemsio data file to netcdf4, it can be done like this:

```
nemsio2nc4.py -v -f 'gfs.t00z.atmf000.nemsio'
mkgfsnemsioctl: /gpfs/hps3/emc/naqfc/noscrub/Barry.Baker/FV3CHEM/exec/mkgfsnemsioctl
cdo: /naqfc/noscrub/Barry.Baker/python/envs/monet/bin/cdo
Executing: /gpfs/hps3/emc/naqfc/noscrub/Barry.Baker/FV3CHEM/exec/mkgfsnemsioctl gfs.t00z.atmf000.nemsio
Executing: /naqfc/noscrub/Barry.Baker/python/envs/monet/bin/cdo -f nc4 import_binary gfs.t00z.atmf000.nemsio.ctl gfs.t00z.atmf000.nemsio.nc4
cdo import_binary: Processed 35 variables [1.56s 152MB]
```

To convert multiple files you can simple use the hot keys available in linux terminals.

```
 nemsio2nc4.py -v -f 'gfs.t00z.atmf0*.nemsio'
 ```
