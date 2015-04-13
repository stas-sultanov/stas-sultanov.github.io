---
layout: post
---

While .NET has several types to work with time, there are times when these types are not very handy to use.

TimeSpan

The type that represents a time unit.

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

The set of extensions methods that allow

```C#
		/// <summary>
		/// Adds <paramref name="timeUnit"/> to the <paramref name="value"/>.
		/// </summary>
		/// <param name="value">The instance of <see cref="DateTime"/>.</param>
		/// <param name="timeUnit">A time interval.</param>
		/// <returns>The new instance of <see cref="DateTime"/> with <paramref name="timeUnit"/> added.</returns>
		public static DateTime Add(this DateTime value, TimeUnit timeUnit)
		
		/// <summary>
		/// Subtracts <paramref name="timeUnit"/> from the <paramref name="value"/>.
		/// </summary>
		/// <param name="value">The instance of <see cref="DateTime"/>.</param>
		/// <param name="timeUnit">A time interval.</param>
		/// <returns>The new instance of <see cref="DateTime"/> with <paramref name="timeUnit"/> subtracted.</returns>
		public static DateTime Subtract(this DateTime value, TimeUnit timeUnit)

		/// <summary>
		/// Returns the smallest <see cref="DateTime"/> value that is greater than or equal to the specified <paramref name="value"/> within the specified <paramref name="timeUnit"/>.
		/// </summary>
		/// <param name="value">The instance of <see cref="DateTime"/>.</param>
		/// <param name="timeUnit">A unit of time.</param>
		/// <returns>The smallest <see cref="DateTime"/> value that is greater than or equal to the specified <paramref name="value"/> within the specified <paramref name="timeUnit"/>.</returns>
		public static DateTime Ceiling(this DateTime value, TimeUnit timeUnit)

		/// <summary>
		/// Returns the largest <see cref="DateTime"/> that less than or equal to the specified <paramref name="value"/> within the specified <paramref name="timeUnit"/>.
		/// </summary>
		/// <param name="value">The instance of <see cref="DateTime"/>.</param>
		/// <param name="timeUnit">A unit of time.</param>
		/// <returns>The largest <see cref="DateTime"/> that less than or equal to the specified <paramref name="value"/> within the specified <paramref name="timeUnit"/>.</returns>
		public static DateTime Floor(this DateTime value, TimeUnit timeUnit)
```

----
