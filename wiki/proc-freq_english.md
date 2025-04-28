<!--
Meta Description: # PROC FREQ: Frequency Analysis in SAS ## Synopsis PROC FREQ is a powerful procedure in SAS used for frequency analysis. It provides insights into cat...
Meta Keywords: frequency, proc, freq, data, tables
-->

# PROC FREQ: Frequency Analysis in SAS

## Synopsis
PROC FREQ is a powerful procedure in SAS used for frequency analysis. It provides insights into categorical data by generating frequency tables, which summarize counts and percentages of distinct values in a dataset.

## Documentation
### Purpose
PROC FREQ is primarily utilized for analyzing categorical variables in SAS datasets. This procedure helps users understand the distribution of data, identify patterns, and detect anomalies.

### Usage
The basic syntax of PROC FREQ is as follows:

```sas
PROC FREQ DATA=dataset-name;
    TABLES variable(s) / options;
RUN;
```

- **DATA=dataset-name**: Specifies the input dataset containing the variables for analysis.
- **TABLES variable(s)**: Lists the categorical variables for which frequency counts are requested.
- **options**: Additional parameters for customizing the output, such as `NOCUM`, `NOFREQ`, `NOPERCENT`, `OUT=`, and `ORDER=`.

### Details
PROC FREQ can handle both single and multiple variables. It generates frequency tables that include:
- **Frequency**: The count of each distinct value.
- **Percent**: The percentage of each value relative to the total.
- **Cumulative Frequency and Percent**: These options can also be specified to show running totals.

PROC FREQ can generate one-way, two-way, or multi-way frequency tables. For two-way tables, it provides cross-tabulations that display the relationship between two categorical variables.

## Examples
### Basic Example
To create a frequency table for a single variable:

```sas
DATA example;
    INPUT gender $;
    DATALINES;
    Male
    Female
    Female
    Male
    Female
    ;
RUN;

PROC FREQ DATA=example;
    TABLES gender;
RUN;
```

### Multi-way Frequency Table
For a two-way frequency table:

```sas
DATA example2;
    INPUT gender $ age_group $;
    DATALINES;
    Male 18-24
    Female 18-24
    Female 25-34
    Male 25-34
    Female 18-24
    ;
RUN;

PROC FREQ DATA=example2;
    TABLES gender*age_group;
RUN;
```

### Output to a New Dataset
To output the frequency counts to a new dataset:

```sas
PROC FREQ DATA=example OUT=freq_output;
    TABLES gender;
RUN;
```

## Explanation
When using PROC FREQ, common pitfalls include:
- **Missing Values**: By default, missing values are included in frequency counts. Use the `MISSING` option to change this behavior.
- **Variable Type**: Ensure that the variables specified are categorical. Continuous variables may not provide meaningful results in a frequency analysis.
- **Large Datasets**: For large datasets, PROC FREQ may result in extensive output. Consider using the `OUT=` option to manage the output more effectively.

Additionally, users should be aware of the implications of small sample sizes when interpreting results, as they may lead to misleading conclusions.

## One Line Summary
PROC FREQ in SAS is utilized for generating frequency tables that summarize the distribution of categorical data, providing essential insights into data patterns and relationships.