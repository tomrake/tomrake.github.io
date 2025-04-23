---
layout: post
title: Smoothing data in R
catagories: [R]
---
## Smooth six months twice daily data in R

The data is entered on a LibreOffice spread sheet, and read into R wih
`read_ods()`.  I adjust the time data like this:

```R
data$Time <- as.POSIXct(strptime(data$Time , "%m/%d/%y %I:%M %p"))
data$TimeCode <- as.numeric(data$Time)
```

### My goal

I want to average all items, within a averaging time window of a given size, for the entire data set,
the window starts at the first day of the data set and is advanced a single day until
the window is beyond the last day of the data set.

### Problem 1 - initial conditions

Find the first and last whole day of the dataset.

window_size

dataset_start_day
dataset_end_day

### Problem 2 - The Increment

Increment the window, day by day


### Problem 3 - Collect the averages.

## Report and graph


