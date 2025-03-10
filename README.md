# Economic Data Processing R Library

This library provides R functions designed to simplify downloading, processing, and analyzing economic time series data from various sources including the Bureau of Labor Statistics (BLS), the Bureau of Economic Analysis (NIPA, BEA), and the Federal Reserve Economic Data (FRED). It also includes tools for projecting time series data using log-linear models.

## Functions and Examples

### 1. `getBLSFiles`
- **Purpose**: Downloads and processes data from the Bureau of Labor Statistics (BLS).
- **Example**:
```r
bls_data <- getBLSFiles(data_source = "cpi", email = "user@example.com")
```

### 2. `getFRED`
- **Purpose**: Downloads and merges economic data series from the Federal Reserve Economic Data (FRED).
- **Example**:
```r
fred_data <- getFRED(variables = c("GDP", "CPIAUCSL"), rename_variables = c("gdp", "cpi"), lagged = c(FALSE, TRUE))
```

### 3. `getPCEInflation`
- **Purpose**: Loads and processes Personal Consumption Expenditures (PCE) data.
- **Example**:
```r
pce_data <- getPCEInflation("M")
```
- The parameter `"M"` specifies monthly data frequency. Use `"Q"` for quarterly data.

### 4. `getNIPAFiles`
- **Purpose**: Downloads and formats BEA NIPA data files.
- **Example**:
```r
nipa_data <- getNIPAFiles(type = "Q")
```

### 4. `logLinearProjection`
- **Purpose**: Performs log-linear projections on historical data.
- **Example**:
```r
projected_values <- logLinearProjection(tbl = df, date_col = "date", value_col = "gdp", start_date = "2020-01-01", end_date = "2021-01-01")
```

## Installation

Install from GitHub:

```r
library(devtools)
install_github("<your-github-username>/<repository-name>")

library(<your-library-name>)
```

Replace `<your-github-username>`, `<repository-name>`, and `<your-library-name>` accordingly.

## Dependencies

- dplyr
- tidyr
- readr
- purrr
- rlang
- stringi

## License

This library is distributed under the MIT License. The MIT license permits reuse of software under permissive conditions, provided that all copies include the license terms and the copyright notice.

