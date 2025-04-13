---
layout: post
title: Smoothing Date formats
---
## Whats in a day?
86400 Seconds

## When do seconds start counting?

January 1, 1970 00:00:00 GMT is the zero second.

That is on 2019-05-01 08:39:00 there have been 1541598420 seconds since Jan 1, 1970

## R dates are the number of days since January 1, 1970

This means the numeric date time is date-number*86400

The earliest time-code is `min(data$TimeCode)` and the last time-code in max(data$TimeCode). The begining data-time-window time-code is `86400*as.numeric(min(data$Date))` the ending date-time-window time-code is the beginning plus the window size in seconds.

The window is advanced by 86400 seconds until the end of the window is larger than `86400*as.numeric(max(data$Date))`

## R code extracting Date and Times.

```R
data$CODE <- factor(data$CODE)
data$Date <- as.Date(strptime(data$Time , "%m/%d/%y %I:%M %p"))
data$Time <- as.POSIXct(strptime(data$Time , "%m/%d/%y %I:%M %p"))
data$TimeCode <- as.numeric(data$Time)
```
