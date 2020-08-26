Instructions Zenodo - download all
================
Ivan Calandra
2020-08-26 12:09:24

  - [Purpose](#purpose)
  - [R instructions](#r-instructions)
      - [Installation](#installation)
      - [Running](#running)
      - [Simple example](#simple-example)
      - [More practical example](#more-practical-example)
  - [Python instructions](#python-instructions)
      - [Installation](#installation-1)
      - [Running](#running-1)
      - [Example](#example)

# Purpose

This document details the steps to download all the files from a given
Zenodo record, either using R or Python.

Note that the code is there only to show the steps taken to download the
file and is therefore not evaluated
(`knitr::opts_chunk$set(eval=FALSE)`).

-----

# R instructions

These instructions use the package
[`zen4R`](https://github.com/eblondel/zen4R) by Emmanuel Blondel.

## Installation

``` r
library(devtools)
install_github("eblondel/zen4R")
```

## Running

``` r
library(zen4R)
download_zenodo("Zenodo_doi", path = "target_directory")
```

## Simple example

``` r
download_zenodo("10.5281/zenodo.3632517", path = "D:/Zenodo")
```

## More practical example

``` r
doi <- "10.5281/zenodo.3632517"
target_folder <- paste0("D:/Zenodo/", basename(doi))
dir.create(target_folder)
download_zenodo(doi, path = target_folder)
```

-----

# Python instructions

These instructions use the package
[`zenodo_get`](https://github.com/dvolgyes/zenodo_get/tree/v1.3.0) by
David Völgyes.  
It requires [Python](https://www.python.org/) 3 to work.

These instructions are for Windows 10. Linux and Mac users will
hopefully be able to adapt them themselves.

All of these commands are to be run in the Windows PowerShell (press the
“Windows” key or click on the “Start” icon, and type “powershell” to
open it).

## Installation

    python -m pip install zenodo_get --user

## Running

    chdir target_directory
    python -m zenodo_get Zenodo_doi -m -e -k

## Example

    mkdir D:\Zenodo\zenodo.3632517
    chdir D:\Zenodo\zenodo.3632517
    python -m zenodo_get 10.5281/zenodo.3632517 -m -e -k
