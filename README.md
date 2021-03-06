[![Travis-CI Build Status](https://travis-ci.org/MahShaaban/aacna.svg?branch=master)](https://travis-ci.org/MahShaaban/aacna)
[![Coverage Status](https://img.shields.io/codecov/c/github/MahShaaban/aacna/master.svg)](https://codecov.io/github/MahShaaban/aacna?branch=master)

# aacna

Data, analysis scripts and output of the analysis of the autophagy and AMPK coexpression in differentiating adipocytes.

## Setting up the docker environment

The analysis was run on a [docker](https://hub.docker.com/r/bcmslab/bioc_wgcna/) image based on the the latest **bioconductor/release\_base2**. Other R packages were added to the image and were made available as an image that can be obtained and launched on any local machine running [docker](https://hub.docker.com/r/bcmslab/bioc_wgcna/).

```bash
$ docker pull bcmslab/bioc_wgcna:20180612
$ docker run -it bcmslab/bioc_wgcna:20180612 bash
```

## Obtaining the source code
The source code is hosted publicly on this repository in a form of research compendium. This includes the functions used throughout the analysis as an R package, the scripts to run the analysis and finally the scripts to reproduce the figures and tables in this manuscript. From within the container, [git](https://git-scm.com) can be used to cloned the source code. The cloned repository contains a sub-folder called `analysis/` which can be used to reproduce the analysis from scratch


* `01.analysis.R` This script loads the required libraries, download the data and run all the steps of the analysis described in the manuscript  

* `figures/` A sub-folder with a separate file for each graph in the manuscript.

* `tables/` A sub-folder with a sepearte file for each table in the manuscript. 

The following code clones the repository containing the source code.

```bash
$ git clone http://github.com/BCMSLab/aacna
```

## Running the analysis

The analysis scripts is organized to be ran using a single [make](https://www.gnu.org/software/make/) command. This will first load the necessary functions and run the main analysis and save the data in an R object `wgcna.rda`. This will be used to generate the figures and graphs. In addition, a log file is generated in the sub-folder 'log/' for each script which can be used for troubleshooting.

To do that, the `make` command should be invoked from withing the `analysis/` sub-folder.

```bash
$ cd aacna/analysis/
$ make
```

## Details of the R environment
The version of **R** that was used to perform this analysis is the 3.4.2 (2017-09-28) on `x86\_64-pc-linux-gnu`. The `DESCRIPTION` file in the main repository contains further details about the dependencies and the license of this work.

## More

* Published paper, [here](http://www.mdpi.com/1422-0067/19/6/1808/htm)
