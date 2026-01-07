# meboot

[![CI](https://github.com/OVVO-Financial/meboot/actions/workflows/ci.yml/badge.svg)](https://github.com/OVVO-Financial/meboot/actions/workflows/ci.yml)

## Overview

`meboot` provides maximum entropy bootstrap utilities for time series and panel data.
It generates an ensemble of dependent resamples without assuming stationarity,
which supports downstream inference workflows that rely on the ergodic and central
limit theorems described by Vinod (2004).

## Features

- Maximum entropy bootstrap for univariate and multivariate time series.
- Panel-data support via `meboot.pdata.frame`.
- Convenience helpers for convergence checks and Spearman correlation constraints.

## Installation

Install the released version from CRAN:

```r
install.packages("meboot")
```

Install the development version from GitHub:

```r
# install.packages("remotes")
remotes::install_github("OVVO-Financial/meboot")
```

## Quick start

```r
library(meboot)

set.seed(123)
series <- rnorm(120)
res <- meboot(series, reps = 499)

# Access the bootstrap ensemble
ensemble <- res$ensemble
```

For panel data, pass a `pdata.frame` (from the `plm` package) to
`meboot.pdata.frame` to generate resamples per entity.

## Documentation

- Package manual: run `?meboot` in an R session after installation.
- Vignettes in `vignettes/` provide extended examples and theory.

## Citation

If you use `meboot` in academic work, please cite:

Vinod, H. D. (2004). Maximum entropy ensembles for time series inference in
financial econometrics. *Journal of Empirical Finance*, 11(5), 857-872.
https://doi.org/10.1016/j.jempfin.2003.06.002

## License

`meboot` is licensed under the GPL (>= 2). See the `DESCRIPTION` file for
details.

## Contributing

Issues and pull requests are welcome. Please include a reproducible example and
session information where relevant.
