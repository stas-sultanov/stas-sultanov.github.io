---
layout: post
---

This post will cover functionality of the ``` BaseEncoding ``` class.

##BaseEncoding class
Provides functionality to encode and decode data using BaseN encoding.
Uses lookup tables to speedup decoding of the data.
Supports following encodings:

* [Base64](https://en.wikipedia.org/wiki/Base64): Lex, MIME, URL
* [Base32](https://en.wikipedia.org/wiki/Base32): Crockford, Hex
* Base16

Supports writing of custom encodings.

#####Encode and decode

```C#
	class Program
	{
		static void Main()
		{
			// 0 get some bytes to test
			var initialData = Encoding.UTF8.GetBytes("some text");

			// 1 encode data
			var encodedData = Base64Encoding.Mime.Encode(initialData);

			// 2 decode data
			var decodedData = Base64Encoding.Mime.Decode(encodedData);

			// 3 get string representation of the data
			var actualData = Encoding.UTF8.GetString(decodedData);

			// 3 write results
			Console.WriteLine($"Encoded data: '{encodedData}'\r\nDecoded data: '{actualData}'");
		}
	}

```

result will be the following:

```
Encoded data: 'c29tZSB0ZXh0'
Decoded data: 'some text'
```

----
