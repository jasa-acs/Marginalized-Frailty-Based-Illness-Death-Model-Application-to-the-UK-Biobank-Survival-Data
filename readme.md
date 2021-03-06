# Marginalized Frailty-Based Illness-Death Model: Application to the UK-Biobank Survival Data

# Author Contributions Checklist Form

## Data


### Abstract 

UK Biobank is a national and international health resource following the
health and well-being of 500,000 volunteer participants and provides
health information, which does not identify them, to approved
researchers in the UK and overseas, from academia and industry. It aims
to improve the prevention, diagnosis and treatment of a wide range of
serious and life-threatening illnesses – including cancer, heart
diseases, stroke and more.

### Availability

The data will not become publicly available. It is open only to
bona-fide scientists undertaking health-related research that is in the
public good. Access to the data is granted only upon application to the
UK Biobank organization.

### Description 

Since the UK Biobank data cannot be publicly published, we provide a
pseudo-dataset, similar to the datasets generated for the simulation
studies. The code for the generation of such datasets is also provided
separately as an R code.

## Code

### Abstract 

We uploaded several code files:

Codes for data generation: available for 3 kinds of frailty
distributions (Gamma – the main simulations, and Inverse Gaussian and
Positive Stable – for sensitivity analysis). During data generation,
users may determine their preferred parameters.

Codes for data analysis:

One cpp file is provided for loading the required functions into the
main estimation procedure, and another R code for the main estimation
procedure. The dataset is inserted into the estimating wrapper function,
with instructions of usage provided within the code itself and in the
Readme file.

### Description 

The code is written in R. MIT license.

Github repository: https://github.com/nirkeret/frailty-LTRC

Required libraries:

-   "survival" (Requires R (&gt;= 3.4.0))

-   "Rcpp"

-   "parallel" (if one wants to perform parallel computation)

-   "Brobdingnag" (Requires R (≥ 2.13.0)

-   "statmod" (for sampling from the inverse Gaussian distribution,
    requires R (≥ 3.0.0))

### Optional Information 

A part of the code (the computation intensive part) can be parallelized
to several cores in order to save computation time.

## Instructions for Use


### Reproducibility 

All tables in the Simulation Study section can be reproduced (main
results and sensitivity analysis).

In order to reproduce a table, datasets should be generated with the
corresponding parameters. Results were mostly collected under seeds
1-100. In order to reproduce a table, 100 datasets, using seeds 1-100
should be generated, and then inserted to the estimation function.

It may take 3-5 hours to analyze a single 5000 observation dataset if no
parallelization is used. Each bootstrap round will require about the
same amount of time. If a higher tolerance for convergence is chosen,
less time will be required (the default tolerance is 0.001 and the
procedure stops when
$\frac{|\text{new\ log} - \text{likelihood} - \text{last\ log} - likelihood\ |}{|last\ log - likelihood\ |\ } < Tol$,
or when 100 iterations have been performed.

