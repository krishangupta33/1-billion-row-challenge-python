# One Billion Row Challenge 💪

This project tackles the challenge of processing a massive dataset containing one billion rows of temperature measurements from various weather stations. The goal is to efficiently calculate the minimum, mean, and maximum temperature for each weather station.


## Challenge Description

The challenge involves processing a text file containing one billion rows of temperature measurements. Each row consists of a weather station name and a temperature value, separated by a semicolon (`;`). The task is to calculate the minimum, mean, and maximum temperature for each weather station efficiently.

## Dataset

The dataset used in this project contains one billion rows, with each row representing a temperature measurement for a specific weather station. The file size is > 13GB. You can generate the dataset by running the generate_data.py script present in the data directory.

## Implementations

Several implementations were explored to tackle this challenge, each utilizing different libraries and techniques. I ran these implementation on 16GB RAM, M2 Pro 14" Macbook. The implementations are as follows:


### 1- Pure Python

The pure Python implementation reads the dataset line by line, processes each row, and calculates the statistics for each weather station using dictionaries. It utilizes the `tqdm` library for progress tracking.

**Elapsed Time:** 594.89 seconds (~10 minutes)

### 2- Pandas

The Pandas implementation leverages the power of the Pandas library to process the dataset in chunks. It reads the data in smaller portions, calculates the statistics for each chunk, and then aggregates the results to obtain the final statistics for each weather station.

**Elapsed Time:** 155.37 seconds

### 3- Dask

The Dask implementation utilizes the Dask library for parallel processing. It reads the dataset in chunks using Dask's distributed computing capabilities, calculates the statistics for each chunk, and then combines the results to obtain the final statistics for each weather station.

**Elapsed Time:** 57.12 seconds

### 4- Polars

The Polars implementation utilizes the Polars library, which is designed for fast data processing. It reads the dataset using lazy evaluation, groups the data by weather station, and calculates the statistics using efficient aggregation functions. Streaming mode is enabled to optimize memory usage.

**Elapsed Time:** 27.80 seconds

### 5- DuckDB

The DuckDB implementation leverages the DuckDB library, which is an embedded SQL database engine. It reads the dataset from a Parquet file and performs the aggregations directly using SQL queries. DuckDB's columnar storage and query optimization techniques contribute to its fast performance.

**Elapsed Time:** 7.18 seconds



## Results

The implementations showcase different approaches to processing a large dataset efficiently. The elapsed times for each implementation are as follows:

| Implementation | Time Elapsed |
| --- | --- |
| Pure Python | 594.89 seconds |
| Pandas | 155.37 seconds |
| Dask | 57.12 seconds |
| Polars | 27.80 seconds |
| DuckDB | 7.18 seconds |


DuckDB demonstrated the fastest performance, followed by Polars and Dask. The pure Python implementation took the longest time due to its iterative nature and lack of optimizations.

## Requirements

To run the code in this project, you need to have the following dependencies installed:

- Python (version 3.6 or higher)
- Pandas
- Polars
- DuckDB
- Dask
- tqdm

You can install the required libraries using pip:

```
pip install pandas polars duckdb dask tqdm
```

## Usage

1. Clone the repository:

```
git clone https://github.com/krishangupta33/1-billion-row-challenge-python.git
```

2. Go to the project directory


3. Run generatedata.ipynb to generate `measurements.txt` and `measurements.parquet` file in the `data` directory.

4. Run the desired implementation code block from `1brc.ipynb`

5. The script will process the dataset and display the elapsed time and the calculated statistics for each weather station/city.

## Contributing

Contributions to this project are welcome! If you have any ideas, suggestions, or improvements, please open an issue or submit a pull request. Make sure to follow the existing code style and provide clear descriptions of your changes.

