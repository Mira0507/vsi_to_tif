# vsi_to_tif

This repository is designed to convert multiple image files with the `vsi` format to 
[OME-TIFF](https://docs.openmicroscopy.org/ome-model/5.6.3/ome-tiff/) at once using 
[Snakemake](https://snakemake.readthedocs.io/en/stable). The `vsi` image files generated 
using the [Olympus VS200 scanner](https://www.olympus-global.com/news/2019/nr01430.html) 
have limited compatibility with image processing tools. Converting individual `vsi` 
images using [Fiji](https://imagej.net/software/fiji/) or 
[QuPath](https://qupath.github.io/) has been a common solution with substantial effort and time, 
depending on the input load. Here, I’d like to propose a simple Snakemake pipeline 
that allows parallel conversion of multiple input `vsi` images at once.

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


