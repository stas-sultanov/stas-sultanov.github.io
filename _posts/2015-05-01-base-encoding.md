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
		static void Main(String[] args)
		{
			var initialData = Encoding.UTF8.GetBytes("some text");

			var encodedData = Base64Encoding.Mime.Encode(initialData);

			var decodedData = Base64Encoding.Mime.Decode(encodedData);

			var actualData = Encoding.UTF8.GetString(decodedData);

			Console.WriteLine("Encoded data: '{0}'\r\nDecoded data: '{1}'", encodedData, actualData);
		}
	}

```

result will be the following:
Encoded data: 'c29tZSB0ZXh0'
Decoded data: 'some text'
