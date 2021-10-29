# Analyzing Stock With VBA Macros

-*Matt Hardy, 2021*

## Overview of Project

### Background

-Our client, Steve, wants our help creating an efficient way to analyze green energy stocks.  Steve's goal is to help his parents diversify their investment portfolio and improve their investment strategy with data-driven decision making.  Currently, all of Steve's parent's holdings are in Daqo (DQ).  

### Parameters

-Our source data includes ticker data from 12 different green energy stocks, including DQ, spanning the years 2017.  We created an easy to use click-button interface that would analyse the volume and returns of those stocks, and display them in an ease-to-read format.  Upon analysis of that subroutine (shown below), the runtime of the code suggested that refactoring the code would be benificial before applying the macro on a larger scale.  While fully operational, the original code took well over 1 second to analyze only 12 stocks.  If applied to thousands of stocks, the macro would take an annoying long time to run.

## Results

### Original Code

![ORIGINAL_CODE](/stock-analysis/Resources/full_originalcode.PNG)

### Results of Original Code

![ORIGINAL_RUNTIMES](/stock-analysis/Resources/original_runtime_gallery.PNG)
