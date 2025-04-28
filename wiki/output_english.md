<!--
Meta Description: # OUTPUT Statement in SAS: A Comprehensive Guide ## Synopsis The OUTPUT statement in SAS is used to control the output of data from a DATA step or a p...
Meta Keywords: output, data, statement, dataset, sas
-->

# OUTPUT Statement in SAS: A Comprehensive Guide

## Synopsis
The OUTPUT statement in SAS is used to control the output of data from a DATA step or a procedure, allowing users to specify which observations to write to a new data set or to the output window.

## Documentation
The OUTPUT statement is integral to data manipulation in SAS, enabling users to manage the flow of data efficiently. It can be used to create new datasets or modify existing ones by specifying conditions under which observations should be written out. 

### Purpose
- **Data Management**: The OUTPUT statement helps in creating subsets of data or aggregating data by controlling what gets written to a dataset.
- **Custom Output**: Users can define their output to include specific variables or observations based on conditions.

### Usage
The basic syntax for the OUTPUT statement is:

```sas
OUTPUT <data-set-name>;
```

- **data-set-name**: This optional parameter allows you to specify a name for the new dataset where the output will be written. If omitted, the data will be written to the current output dataset.

### Details
- The OUTPUT statement can be used multiple times within a DATA step to output different records based on specified criteria.
- You can use conditional logic to control when an observation should be written to the output dataset.
- It is often used in conjunction with other statements such as IF-THEN to filter data.

## Examples
### Example 1: Basic OUTPUT Statement
```sas
data output_example;
    set input_data;
    if age > 30 then output;
run;
```
This example creates a new dataset `output_example` that includes only those observations from `input_data` where the age is greater than 30.

### Example 2: OUTPUT with Multiple Data Sets
```sas
data output_multiple;
    set input_data;
    if age < 20 then output young;
    else if age >= 20 and age <= 40 then output middle_aged;
    else output old;
run;
```
In this case, the OUTPUT statement is used to create three different datasets based on age categories: `young`, `middle_aged`, and `old`.

## Explanation
### Common Pitfalls
- **Not Specifying a Dataset**: If no dataset is specified in the OUTPUT statement, SAS will output to the current dataset, which can lead to confusion if not intended.
- **Conditional Logic**: Ensure that the conditions used in conjunction with the OUTPUT statement are correctly defined to avoid unintended omissions in the output dataset.
- **Multiple Outputs**: When using multiple OUTPUT statements, be cautious of overwriting datasets with the same name.

### Gotchas
- The OUTPUT statement can only be used within a DATA step; it is not applicable in PROC steps.
- If you want to output to the default output dataset as well as create a new one, you need to include both OUTPUT statements.

## One Line Summary
The OUTPUT statement in SAS is a powerful tool for controlling the flow of data output to datasets, allowing for tailored data management and manipulation.