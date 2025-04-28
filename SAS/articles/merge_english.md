<!--
Meta Description: # MERGE in SAS: Combining Datasets Efficiently ## Synopsis The `MERGE` statement in SAS is a powerful feature that allows users to combine multiple da...
Meta Keywords: data, merge, datasets, run, one
-->

# MERGE in SAS: Combining Datasets Efficiently

## Synopsis
The `MERGE` statement in SAS is a powerful feature that allows users to combine multiple datasets into a single dataset based on one or more common key variables, facilitating data analysis and reporting.

## Documentation
The `MERGE` statement is primarily used in the DATA step of SAS programming to concatenate datasets either by row or by specified keys. When combining datasets, SAS requires that the datasets be sorted by the key variables specified.

### Purpose
The primary purpose of the `MERGE` statement is to integrate data from different sources, allowing analysts to create comprehensive datasets that can be used for further analysis or visualization.

### Usage
The basic syntax of the `MERGE` statement is as follows:

```sas
DATA output_dataset;
    MERGE dataset1 dataset2;
    BY key_variable;
RUN;
```

- **output_dataset**: The name of the new dataset created from merging.
- **dataset1, dataset2**: The datasets being merged.
- **key_variable**: The variable(s) that are common between the datasets and used for merging.

### Details
1. **Sorting**: Before using the `MERGE` command, ensure that the datasets are sorted by the key variables using the `PROC SORT` procedure.
2. **One-to-One Merge**: If both datasets have unique key values, a one-to-one merge occurs, where records in both datasets align perfectly.
3. **One-to-Many/Many-to-One Merge**: In cases where one dataset has multiple records for a key variable, SAS will create multiple records in the resulting dataset for each matching key.
4. **Handling Missing Values**: If a record in one dataset does not have a matching record in the other, SAS fills in the missing values for the variables from the non-matching dataset with a missing value (represented as a dot).

## Examples

### Example 1: Simple Merge
```sas
DATA employees;
    INPUT EmployeeID Name $;
    DATALINES;
1 John
2 Sarah
3 Mike
;
RUN;

DATA salaries;
    INPUT EmployeeID Salary;
    DATALINES;
1 50000
2 60000
3 55000
;
RUN;

PROC SORT DATA=employees; BY EmployeeID; RUN;
PROC SORT DATA=salaries; BY EmployeeID; RUN;

DATA merged_data;
    MERGE employees salaries;
    BY EmployeeID;
RUN;

PROC PRINT DATA=merged_data; RUN;
```

### Example 2: One-to-Many Merge
```sas
DATA departments;
    INPUT DepartmentID DepartmentName $;
    DATALINES;
1 HR
2 IT
;
RUN;

DATA employees;
    INPUT EmployeeID Name $ DepartmentID;
    DATALINES;
1 John 1
2 Sarah 2
3 Mike 1
;
RUN;

PROC SORT DATA=departments; BY DepartmentID; RUN;
PROC SORT DATA=employees; BY DepartmentID; RUN;

DATA merged_data;
    MERGE employees departments;
    BY DepartmentID;
RUN;

PROC PRINT DATA=merged_data; RUN;
```

## Explanation
Common pitfalls when using the `MERGE` statement include:

- **Unsuitable Data Sorting**: Not sorting the datasets by the key variables before merging can lead to unexpected results or errors.
- **Non-Matching Keys**: Ensure all key variables exist in both datasets to avoid losing valuable data.
- **Duplicate Keys**: If both datasets contain duplicate key values, the resulting dataset may have more records than anticipated, leading to potential confusion in data interpretation.
  
Always verify the merged dataset to ensure it meets expectations and reflects the intended data structure.

## One Line Summary
The `MERGE` statement in SAS enables the efficient combination of multiple datasets based on shared key variables, facilitating comprehensive data analysis.