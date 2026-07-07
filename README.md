# Time Series Analysis with Pandas — Coursework

## Project Overview
The repository contains my coursework notebook covering **Time Series Analysis in pandas**. It works through a series of guided recipes that build up pandas' date/time handling capabilities — from basic `datetime` vs. pandas `Timestamp` differences, through slicing, `DatetimeIndex`-only methods, resampling/grouping by time, and finally `merge_asof` for time-based joins.

The notebook uses real-world **Denver crime and traffic accident data**, along with supporting Denver population and employee datasets, to demonstrate each technique on practical, non-trivial data rather than toy examples.

## Topics Covered
1. Understanding the difference between Python's `datetime` and pandas' date tools
2. Slicing time series intelligently
3. Using methods that only work with a `DatetimeIndex`
4. Counting the number of weekly crimes
5. Aggregating weekly crime and traffic accidents separately
6. Measuring crime by weekday and year
7. Grouping with anonymous (lambda) functions on a `DatetimeIndex`
8. Grouping by a `Timestamp` combined with another column
9. Finding the last time crime was 20% lower, using `merge_asof`

## Dataset Information
| File | Description |
|---|---|
| `crime.h5` | Denver crime and traffic accident records (HDF5 format), indexed by report date |
| `denver_pop.csv` | Denver population data by year, used for per-capita crime rate context |
| `employee.csv` | Supplementary dataset used to illustrate general date/time operations |

> The original notebook references local file paths (e.g. `C:\Users\...\crime.h5`). Before running, update these paths to point to wherever you've placed the source files locally — ideally a `data/` folder alongside the notebook.

## Repository Structure
```
time-series-analysis-pandas/
├── Chapter_10_Time_Series_Analysis.ipynb
├── README.md
└── requirements.txt
```
> Datasets are intentionally excluded from version control. Add a `data/` folder locally (not tracked in this repo) if you want to re-run the notebook yourself.

## Environment Setup
```bash
git clone https://github.com/MUQADAS-03/time-series-analysis-pandas.git
cd time-series-analysis-pandas
pip install -r requirements.txt
jupyter notebook Chapter_10_Time_Series_Analysis.ipynb
```
> `pandas.read_hdf()` requires the `tables` (PyTables) package, which is included in `requirements.txt`.

## Key Concepts Practiced
- Converting and comparing Python `datetime` objects vs. pandas `Timestamp`/`DatetimeIndex`
- Efficient partial-string and slice-based indexing on datetime-indexed data
- Resampling and `groupby` with time-based frequencies (weekly, yearly, weekday)
- Combining a `Timestamp` grouper with a categorical column for multi-level aggregation
- Using `pd.merge_asof()` to join on nearest prior timestamp — useful for comparing current values against historical benchmarks

## Author
**Muqadas Yasin**
