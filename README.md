# vsi_to_tif

This repository is designed to convert multiple image files with the `vsi` format 
to [OME-TIFF](https://docs.openmicroscopy.org/ome-model/5.6.3/ome-tiff/) using 
[Snakemake](https://snakemake.readthedocs.io/en/stable).

## Package installation

Packages were installed using the [Conda](https://docs.conda.io/en/latest/) package manager.
For more detailed information about packages and versions, refer to 
the `env.archived.yaml` file.

## Scripts

- `snakemake/Snakefile`: Running Snakemake pipeline to convert `vsi` to `tif`
- `snakemake/config/config.yaml`: Configuring Snakemake
`snakemake/config/WRAPPER_SLURM`: Enabling Snakemake to run on a cluster. 
The Snakemake profile is cluster-specific. The current wrapper is for the 
[Slurm cluster of NIH Biowulf](https://hpc.nih.gov/docs/userguide.html).
- `snakemake/config/sampletable.txt`: 
Specifying sample names and corresponding input image paths
- `snakemake/image_conversion.Rmd`: 
Wrapper script running `bftools` for image conversion


