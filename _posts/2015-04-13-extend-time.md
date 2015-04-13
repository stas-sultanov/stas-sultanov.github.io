---
layout: post
---

While .NET has several types to work with time, there are times when these types are not very handy to use.

`TimeSpan` represents a time interval it ticks. In most cases it's fine but when you are working with, for example, reports you are dealing with time units like days, hours, minutes. And it becames not handy to work with time units by using `TimeSpan`

So lets introduce a new type that represents a time unit.

```C#
public enum TimeUnit : long
{
	Microsecond = 10L,
	Millisecond = 10000L,
	Second = 10000000L,
	Minute = 600000000L,
	Hour = 36000000000L,
	Day = 864000000000L
}
```

As you can see this is an enumeration of available fixed time units, where value of the item of the enumeration equals to count of ticks that it represents. As mentioned befour this is #Fixed# time units and it appears that it is imposible to add such time units as `Month` and `Year` becaus count of days in month and year may differ.

The set of extensions methods that allows `TimeUnit` to work with `DateTime`

```C#
/// <summary>
/// Adds <paramref name="timeUnit"/> to the <paramref name="value"/>.
/// </summary>
public static DateTime Add(this DateTime value, TimeUnit timeUnit)

/// <summary>
/// Subtracts <paramref name="timeUnit"/> from the <paramref name="value"/>.
/// </summary>
public static DateTime Subtract(this DateTime value, TimeUnit timeUnit)

/// <summary>
/// Returns the smallest <see cref="DateTime"/> value that is greater than
/// or equal to the specified <paramref name="value"/> within the specified <paramref name="timeUnit"/>.
/// </summary>
public static DateTime Ceiling(this DateTime value, TimeUnit timeUnit)

/// <summary>
/// Returns the largest <see cref="DateTime"/> that less than
/// or equal to the specified <paramref name="value"/> within the specified <paramref name="timeUnit"/>.
/// </summary>
public static DateTime Floor(this DateTime value, TimeUnit timeUnit)
```

----
