# Country Sales Analysis (Hadoop MapReduce + Hive)

A Big Data project analyzing country-level sales transactions using Hadoop MapReduce for aggregation and Hive for querying.

## Overview

The dataset consists of sales transactions with columns for Transaction ID, Product, Price, and Country. This project uses a Hadoop MapReduce job to count total transactions per country, with additional analysis performed using Hive queries on the same dataset.

## Team Project

This was built as part of a 3-person academic project (Aishwarya Ramanath Shanbhag, Navya Hegde, Shrushti Hegde). My contributions centered on the MapReduce implementation and country-level aggregation logic.

## How It Works

`Sales.java` implements a standard Hadoop MapReduce job:

1. **Map phase**: each line of the input CSV is tokenized by comma, and the Country field is extracted as the map key with a count of 1.
2. **Reduce phase**: counts for each country are summed to produce total transactions per country.

Hive was used separately to run additional exploratory queries on the same dataset (see `report.docx` for query outputs and screenshots).

## Tech Stack

- Java
- Apache Hadoop (MapReduce)
- Apache Hive

## Files

- `sales.java` — Hadoop MapReduce job for counting transactions by country
- `report.docx` — full project report, including Hive query outputs and screenshots

## Running the Project

```bash
javac -classpath $(hadoop classpath) -d . Sales.java
jar -cvf sales.jar -C . .
hadoop jar sales.jar Sales /input/path /output/path
```

## Note

The original Hive queries were preserved only as screenshots in the project report rather than as separate `.hql` script files, so they aren't included here as runnable code.

## Author

Aishwarya Ramanath Shanbhag
