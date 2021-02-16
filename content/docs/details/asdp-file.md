---
title: ".asdp file"
weight: 1
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: true
---

# .asdp file

An `.asdp` file holds the results of a scan as a list of points.
Every line in an `.asdp` file (aside from header lines starting with `#`)
represent a point.

`lidar-driver` sends the measurements in this format and `lidar-client` is
writing those into `.asdp` files. The format is intended to be:
- compact in size, as it travels via serial connection in realtime during a scan
- easy and fast to produce in the driver, for the same reason
- extendable

## v1 reference

### Header lines

- Header lines start with `#`.
- Whitespaces between the starting `#` and the first non-whitespace character are ignored.
- The **first header line must be** `version`:

```
# version 1
```

- The following other headers are used:

```
# x-resolution <INTEGER>
# y-resolution <INTEGER>
# num-rows <INTEGER>
```

- `x-resolution` is the number of points in a row (along the X axis).
- `y-resolution` is the number of points in a **full 360°** column (along the Y axis).
- `num-rows` is the number of rows in the measurement. (Total number of points in measurement = `x-resolution * num-rows`)
- Any other header line is ignored in v1. This essentially means that `#` lines
can be treated as comments.
- All header lines must precede all data lines.

### Data lines

- Data lines can't start with `#`
- Data lines are CSV records (see RFC 4180):

```
<time-ms>,<x-position>,<y-position>,<distance>
```

- `time-ms`: Time in millis (since scanner) when point was captured. Can be used for benchmarkind and analysing performance.
- `x-position`: The position of the scanner along the X (horizontal) axis.
- `y-position`: The position of the scanner along the Y (vertical) axis.
- `dist`: Distance measured in the direction.

- Data lines must be in row-major order.