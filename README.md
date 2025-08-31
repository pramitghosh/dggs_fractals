# Measuring Fractal Dimension using Discrete Global Grid Systems
This repository contains the data and code supporting the results in the manuscript titled as above. A pre-print of the same is available from [arXiv](https://arxiv.org/abs/2506.18175). The analysis is presented in the form of a Quarto Markdown document `workflow_new.qmd`. A rendered HTML page is also hosted here: https://pramitghosh.github.io/dggs_fractals/.

## Data used
The analysis uses a modified Meteosat Third Generation (MTG) FCI Level-2 Cloud Mask (CLM) image customised from the original using EUMETSAT's Data Tailor service and is present as a `.tif` file in the `clouds/` directory. This is shared under CC-BY 4.0 licence with the following attribution: **Contains modified EUMETSAT Meteosat Cloud Mask - MTG - 0 degree product from 2025**.

This data can also be customised and downloaded programmatically from EUMETSAT's Data Tailor web service free of charge (subject to registration on their User Portal). The simplest way to do so is using the EUMDAC library in the CLI mode using the following command:
```
eumdac download -p W_XX-EUMETSAT-Darmstadt,IMG+SAT,MTI1+FCI-2-CLM--FD--x-x---x_C_EUMT_20250315121703_L2PF_OPE_20250315120000_20250315121000_N__C_0073_0000 -c EO:EUM:DAT:0678 --tailor clouds/chain.yml -o clouds/
```

## Pre-requisites
The following libraries are needed to be present on the local machine in order to render the Quarto document successfully.

### Python
This is only required if the satellite image is to be customised afresh:
- EUMDAC v3.0.0 (available through [pip](https://pypi.org/project/eumdac/), [Anaconda](https://anaconda.org/Eumetsat/eumdac) etc.)

### R
The following R packages are required (available via CRAN):
- dggridR v3.1.0
- sf v1.0-21
- sfheaders v0.4.4
- terra v1.8-60
- rnaturalearth v1.1.0
- rnaturalearthdata v1.0.0

Additionally, the following package available from Github needs to be installed.
- h3 v3.7.1: [crazycapivara/h3-r](https://github.com/crazycapivara/h3-r)

## Execution
The Quarto markdown can be rendered to a HTML page among other formats using several means such as the `quarto render` command ([more details here](https://quarto.org/docs/computations/r.html#rendering)).
> [!NOTE]
> Computation of the entire analysis and subsequent rendering takes significant amount of time (~3 hours on 12th Generation Intel Core i7 series processor with 20 cores and 32GB of main memory running on Ubuntu 25.04).

## Results
Results described in the manuscript are available as output of the analysis. Figures presented in the manuscript are also generated.
> [!NOTE]
> Given the nature of the computation and available precision, some results vary negligibly ($`\sim10^{-3}`$) over reach run. However, this does not affect the inference and conclusions drawn from this analysis.
