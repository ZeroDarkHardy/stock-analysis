# Analyzing Stock With VBA Macros

-*Matt Hardy, 2021*

## Overview of Project

### Background

-Our client, Steve, wants our help creating an efficient way to analyze green energy stocks.  Steve's goal is to help his parents diversify their investment portfolio and improve their investment strategy with data-driven decision making.  Currently, all of Steve's parent's holdings are in Daqo (DQ).  

### Parameters

-Our source data includes ticker data from 12 different green energy stocks, including DQ, spanning the years 2017.  We created an easy to use click-button interface that would analyse the volume and returns of those stocks, and display them in an ease-to-read format. After a working subroutine is created, our goal was to optimize the efficiency of that macro by refactoring its code. 

## Results

### Original Code

![ORIGINAL_CODE](https://github.com/ZeroDarkHardy/stock-analysis/blob/main/Resources/full_original_code.PNG)

### Results of Original Code

![ORIGINAL_RUNTIMES](https://github.com/ZeroDarkHardy/stock-analysis/blob/main/Resources/original_runtime_gallery.png)
We can see from our analysis of this sample of stocks that Steve's parents may not have picked a winner in DQ.  While almost all of the stocks in our sample had positive returns in 2017, only two showed positively in 2018 (ENPH and RUN both showed net returns of over 80%).  At the very least, a visual representation of the volitility of this sector of the market should convince our client's parents to diversity their positions.

### Analysis of Original Code

Upon analysis of that subroutine (shown below), the runtime of the code suggested that refactoring the code would be benificial before applying the macro on a larger scale.  While fully operational, the original code took well over 1 second to analyze only 12 stocks.  If applied to thousands of stocks, the macro would take an annoying long time to run.

## Refactoring the Code

- Introduction of a "tickerIndex" variable and 3 output arrays to our subroutine helped avoid nested "For Loops" in our code...
![tickerIndex_variable](https://github.com/ZeroDarkHardy/stock-analysis/blob/main/Resources/steps1a_1b.PNG)
  
- Our tickerVolume variable would be reset to 0 before each loop..
![tickerVolume_zero](https://github.com/ZeroDarkHardy/stock-analysis/blob/main/Resources/steps2a_2b.PNG)

- The tickerIndex could then be referenced as a qualifier in the operating formulas...
![increase_tickerVolume](https://github.com/ZeroDarkHardy/stock-analysis/blob/main/Resources/steps3a_3b_3c_3d.PNG)

- And then finally referenced by all three of our output arrays:
![output_arrays](https://github.com/ZeroDarkHardy/stock-analysis/blob/main/Resources/steps4.PNG)

## Runtimes of Refactored Code

![refactored_runtime_galleries](https://github.com/ZeroDarkHardy/stock-analysis/blob/main/Resources/refactored_runtime_gallery.png)

### Analysis of Refactored Code

- While a little less flashy in the formatting, the new refactored code was *VASTLY* more efficient than our original subroutine, running in just over 1/10th the amount of time!  This should help our client tremendously, should he choose to upscale his analysis to a wider scale of stocks.  (FULL REFACTORED CODE SHOWN AT BOTTOM OF PAGE)

## Summary

- From this clear example, refactoring code within VBA subroutines can produce the desired results much faster upon execution.  However, a risk is present for potentially breaking existing code (which happened several times during the creation of our refactored subroutine).  Given unlimited work time, the benefits of refactoring are self-evident, but shouldn't be pursued if close to a deadline because of a variable risk of encountering time-consuming obstacles.

### Original vs Refactored VBA Script

- In this case, the benefits of using our original code are minimal next to the vastly shortened runtime of the refactored code.  While the original code adds some additional formatting, color, and one additional decimal place as a measure of precision, the refactored code will process almost 10x the amount of data in the same runtime.  However, Steve's parent's may prefer the friendly, colorful formatting, and transposing those conditions to the refactored code should create a negligible difference.

## Refactored Code (Full Updated Script)

![full_refactored_macro](https://github.com/ZeroDarkHardy/stock-analysis/blob/main/Resources/full_refactored_code.PNG)
