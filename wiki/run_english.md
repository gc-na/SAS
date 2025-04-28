<!--
Meta Description: # Understanding the RUN Statement in SAS: A Comprehensive Guide ## Synopsis The RUN statement in SAS is a crucial command that signals the end of a st...
Meta Keywords: run, statement, sas, data, step
-->

# Understanding the RUN Statement in SAS: A Comprehensive Guide

## Synopsis
The RUN statement in SAS is a crucial command that signals the end of a step in a SAS program, enabling the execution of the preceding code. It is essential for executing DATA and PROC steps and ensuring that processes are completed correctly.

## Documentation
The RUN statement serves as a delimiter in SAS programming, indicating that the code preceding it should be executed. This command is fundamental for both DATA steps—where data manipulation occurs—and PROC steps—where various procedures are applied to data.

### Purpose
- To execute SAS code in DATA and PROC steps.
- To ensure that all preceding statements are completed before moving on to the next step.

### Usage
In SAS, the RUN statement is typically placed at the end of a DATA step or a PROC step. Its syntax is simply:

```sas
RUN;
```

### Details
- The RUN statement is not always required, as SAS may automatically execute code when it encounters a new step. However, including it can enhance readability and ensure that the intended execution order is maintained.
- The RUN statement can also be used in combination with other statements for more complex programming tasks.

## Examples
### Example 1: Basic DATA Step
```sas
DATA example_data;
    input name $ age;
    datalines;
Alice 30
Bob 25
;
RUN;
```
In this example, the RUN statement executes the DATA step to create a dataset named `example_data`.

### Example 2: PROC Step
```sas
PROC PRINT DATA=example_data;
RUN;
```
Here, the RUN statement executes the PROC PRINT step, which displays the contents of the `example_data` dataset.

### Example 3: Multiple Steps
```sas
DATA new_data;
    set example_data;
    age_squared = age**2;
RUN;

PROC MEANS DATA=new_data;
    VAR age_squared;
RUN;
```
In this example, each step is concluded with a RUN statement, ensuring each part is executed in sequence.

## Explanation
### Common Pitfalls
- **Omitting the RUN Statement:** While SAS may execute some steps without an explicit RUN statement, not using it can lead to confusion, especially in larger programs. It is best practice to include it for clarity.
- **Order of Execution:** The RUN statement establishes the order of execution. Misplacing it can lead to logical errors in your code.
- **Use in Macro Programs:** When using macros, ensure that RUN statements are appropriately placed to avoid unexpected behavior.

### Additional Notes
- The RUN statement is case-insensitive in SAS, meaning `run;`, `Run;`, and `RUN;` are all valid.
- In interactive sessions, a RUN statement may be automatically added by the SAS environment, but it is still good practice to include it in your code for portability.

## One Line Summary
The RUN statement in SAS is essential for executing DATA and PROC steps, ensuring that the preceding code is completed before proceeding.