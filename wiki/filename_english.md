<!--
Meta Description: # Understanding FILENAME in SAS: The Key to External File Management ## Synopsis The FILENAME statement in SAS is a powerful tool used for assigning a...
Meta Keywords: file, filename, sas, data, external
-->

# Understanding FILENAME in SAS: The Key to External File Management

## Synopsis
The FILENAME statement in SAS is a powerful tool used for assigning a fileref (file reference) to an external file or device, enabling seamless data input and output operations within SAS programs.

## Documentation
The FILENAME statement is essential for managing external files in SAS. By creating a fileref, users can reference external files (such as text files, CSVs, or spreadsheets) without specifying the full path each time. This flexibility simplifies file handling and enhances code portability.

### Purpose
- To create a logical reference to an external file or device.
- To manage file access for reading and writing data.
- To enable the use of external data sources within SAS procedures.

### Usage
The basic syntax for the FILENAME statement is as follows:

```sas
FILENAME fileref 'external-file-path';
```

- **fileref**: A user-defined name (up to 8 characters) that represents the external file.
- **external-file-path**: The complete path to the file or device, enclosed in single or double quotes.

### Options
The FILENAME statement can also include multiple options:
- **DISK**: Specifies the file is on disk.
- **TEMP**: Indicates the file is temporary and will be deleted after the SAS session ends.
- **URL**: Allows access to files on the web.

## Examples
### Example 1: Basic FILENAME Usage
```sas
FILENAME myfile '/path/to/your/data.txt';
DATA mydata;
    INFILE myfile;
    INPUT var1 var2 var3;
RUN;
```
In this example, the FILENAME statement assigns the fileref `myfile` to a text file located at `/path/to/your/data.txt`. The DATA step then reads data from this file.

### Example 2: Using TEMP Option
```sas
FILENAME tempfile TEMP;
DATA _NULL_;
    FILE tempfile;
    PUT 'This is a temporary file.';
RUN;
```
Here, `tempfile` is a temporary file that will be deleted at the end of the session. The DATA step writes a line of text to it.

### Example 3: Accessing a URL
```sas
FILENAME myurl URL 'http://example.com/data.csv';
PROC IMPORT DATAFILE=myurl OUT=mydata DBMS=CSV REPLACE;
RUN;
```
This example demonstrates how to read a CSV file from a URL using the FILENAME statement.

## Explanation
When using the FILENAME statement, users should be mindful of the following:
- Ensure the file path is correct; otherwise, SAS will raise an error.
- Filerefs are case-sensitive on some operating systems (like UNIX), so consistency is key.
- Always remember to free up filerefs using `FILENAME fileref CLEAR;` when they are no longer needed, especially in long-running sessions or applications.
- Temporary files created with the TEMP option will not be accessible outside the current SAS session.

## One Line Summary
The FILENAME statement in SAS is used to assign a logical reference to an external file, streamlining data input and output operations.