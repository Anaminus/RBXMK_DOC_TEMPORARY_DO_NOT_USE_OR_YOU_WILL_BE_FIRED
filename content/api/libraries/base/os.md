+++
weight = 100
title = "os"
+++

The **os** library contains functions related to the operating system.

<div class="api-list one two">

| Item | Kind | Description |
| --- | --- | --- |
| [clock](#clock) | Function | Returns the CPU time. |
| [date](#date) | Function | Returns the current time. Returns the time as a table. Returns the time as a formatted string. |
| [difftime](#difftime) | Function | Returns the difference between two times. |
| [time](#time) | Function | Returns a numeric time. |

</div>

# Functions

----

## clock

 `os.clock(): number`

The **clock** function returns, approximately, the seconds of CPU time
used by the program.

## date

 `os.date(): string`

The **date** function returns a string-representation of the current
time.

 `os.date(format: string ["*t", !*t], time: number?): {day: integer, hour: integer?, isdst: boolean?, min: integer?, month: integer, sec: integer?, wday: integer?, yday: integer?, year: integer}`

The **date** function returns the time as a table with a number of fields
for each component:

| Field | Notes |
| --- | --- |
| year | 4 digits |
| month | 1 - 12 |
| day | 1 - 31 |
| hour | 0 - 23 |
| min | 0 - 59 |
| sec | 0 - 61 |
| wday | Day of the week, 1 - 7 starting on Sunday. |
| yday | Day of the year, 1 - 366. |
| isdst | Whether Daylight Saving Time is active. |

If *time* is specified, then it specifies the time to be formatted.
Otherwise, the current time is used. See os.time for a description of this
value.

 `os.date(format: string, time: number?): string`

The **date** function returns the formatted according to *format*,
which has the same rules as the C function strftime.

If *time* is specified, then it specifies the time to be formatted.
Otherwise, the current time is used. See os.time for a description of this
value.

## difftime

 `os.difftime(t2: number, t1: number): number`

The **difftime** function returns the number of seconds between *t2*
and *t1*. On most systems, this value is exactly equal to `t2 -
t1`.

## time

 `os.time(t: {day: integer, hour: integer?, isdst: boolean?, min: integer?, month: integer, sec: integer?, year: integer}?): number`

The **time** function returns a numeric time corresponding to the fields
of *t*. If *t* is unspecified, then the current time is returned.

On most systems, the returned value is the relative to the UNIX epoch. On
others, the meaning is unspecified, and may only be passed to os.date and
os.difftime.