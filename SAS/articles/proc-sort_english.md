<!--
Meta Description: # PROC SORT in SAS: Efficiently Organizing Your Data ## Synopsis PROC SORT is a key procedure in SAS (Statistical Analysis System) used to sort data s...
Meta Keywords: data, proc, sort, variables, run
-->

# PROC SORT in SAS: Efficiently Organizing Your Data

## Synopsis
PROC SORT is a key procedure in SAS (Statistical Analysis System) used to sort data sets efficiently. It allows users to organize their data in ascending or descending order based on one or more specified variables.

## Documentation

### Purpose
PROC SORT is primarily utilized to arrange observations in a data set according to the values of one or more variables. Sorting data is a fundamental step in data analysis and prepares the data for further processing, reporting, or merging with other data sets.

### Usage
The basic syntax of PROC SORT is as follows:

```sas
PROC SORT DATA=input-data-set OUT=output-data-set;
    BY variable(s);
RUN;
```

- **DATA**: Specifies the input data set to be sorted.
- **OUT**: (Optional) Names the output data set containing the sorted data. If not specified, the original data set is replaced.
- **BY**: Indicates one or more variables by which the data should be sorted. Multiple variables can be specified, separated by spaces.

### Details
- By default, PROC SORT sorts data in ascending order. To sort in descending order, the `DESCENDING` option can be used before the variable name in the BY statement.
- PROC SORT automatically handles missing values, placing them at the beginning (for ascending order) or end (for descending order).
- When sorting by multiple variables, the order of variables in the BY statement determines the hierarchy of sorting.
- The sorted data set retains the original variable attributes.

## Examples

### Example 1: Basic Sorting
```sas
DATA example;
    INPUT Name $ Score;
    DATALINES;
    John 85
    Alice 90
    Bob 78
    Carol 92
    ;
RUN;

PROC SORT DATA=example OUT=sorted_example;
    BY Score;
RUN;

PROC PRINT DATA=sorted_example;
RUN;
```

### Example 2: Sorting in Descending Order
```sas
PROC SORT DATA=example OUT=sorted_example_desc;
    BY DESCENDING Score;
RUN;

PROC PRINT DATA=sorted_example_desc;
RUN;
```

### Example 3: Sorting by Multiple Variables
```sas
DATA example_multi;
    INPUT Name $ Age Score;
    DATALINES;
    John 25 85
    Alice 22 90
    Bob 25 78
    Carol 22 92
    ;
RUN;

PROC SORT DATA=example_multi OUT=sorted_example_multi;
    BY Age Score;
RUN;

PROC PRINT DATA=sorted_example_multi;
RUN;
```

## Explanation
Common pitfalls when using PROC SORT include:
- Forgetting to specify the `OUT` option, which can result in the original data set being overwritten unintentionally.
- Incorrectly assuming that PROC SORT will automatically handle duplicates. To remove duplicates, the `NODUPKEY` option can be used.
- Misordering of variables in the BY statement, which can lead to unexpected sorting results.

It’s also important to note that if you are working with large datasets, sorting can be resource-intensive. Monitoring system performance during the sort operation is advisable.

## One Line Summary
PROC SORT in SAS is a powerful procedure for organizing data sets by one or more variables in ascending or descending order.