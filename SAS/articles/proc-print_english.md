<!--
Meta Description: # PROC PRINT: A Comprehensive Guide to Printing SAS Data Sets ## Synopsis PROC PRINT is a powerful procedure in SAS that allows users to display the c...
Meta Keywords: data, print, proc, sas, example
-->

# PROC PRINT: A Comprehensive Guide to Printing SAS Data Sets

## Synopsis
PROC PRINT is a powerful procedure in SAS that allows users to display the contents of a SAS data set in a tabular format. It is frequently used for data exploration and validation.

## Documentation
### Purpose
PROC PRINT is primarily used to output SAS data sets in a readable format. It is ideal for quickly reviewing data, checking for errors, and providing a visual representation of data attributes.

### Usage
To employ PROC PRINT, the basic syntax is as follows:

```sas
PROC PRINT DATA=<dataset>;
RUN;
```
- `<dataset>` refers to the name of the SAS data set you wish to print.

### Details
- **DATA= option**: Specifies the data set to print. This option is mandatory.
- **VAR statement**: Allows users to specify particular variables to display in the output.
- **WHERE statement**: Enables filtering of data before printing, based on specified conditions.
- **ID statement**: Designates one or more variables to appear as row identifiers in the output.
- **OBS= option**: Controls the number of observations printed.

PROC PRINT can be customized with various options to enhance the output, such as formatting values, adding titles, or modifying the appearance of the printed table.

## Examples
### Basic Example
```sas
DATA example;
    INPUT Name $ Age Height;
    DATALINES;
    John 25 5.9
    Jane 30 5.5
    Mike 35 6.1
    ;
RUN;

PROC PRINT DATA=example;
RUN;
```
This example creates a simple data set named `example` and prints its contents.

### Using VAR and ID Statements
```sas
PROC PRINT DATA=example;
    VAR Name Age;
    ID Name;
RUN;
```
In this example, only the variables `Name` and `Age` are printed, with `Name` serving as the row identifier.

### Filtering Data with WHERE Statement
```sas
PROC PRINT DATA=example;
    WHERE Age > 28;
RUN;
```
This example prints only those observations where the `Age` is greater than 28.

## Explanation
While PROC PRINT is straightforward, users may encounter a few common pitfalls:
- **Missing Data**: If a data set contains missing values, PROC PRINT will still display the records, which may lead to misinterpretation if not noticed.
- **Large Data Sets**: Printing large data sets can result in overwhelming output; it is advisable to use the `OBS=` option to limit the number of printed rows.
- **Column Widths**: Default widths for printed columns may not accommodate long variable names or values, leading to truncated output. Users can adjust column widths using formatting options.

## One Line Summary
PROC PRINT is a fundamental SAS procedure that provides an efficient way to display and review the contents of a data set in a tabular format.