---
layout: post
---

There are times when comes a need to convert some data to base-n encoding.

##Base-N encodings:
in order of
* [Base85](https://en.wikipedia.org/wiki/Ascii85)
* [Base64](https://en.wikipedia.org/wiki/Base64)
* [Base32](https://en.wikipedia.org/wiki/Base32)
* Base-16

Unfortunately the **Tester-Doer** pattern has several issues:

#####Issue #1
The implicitly captured closure might occur.
The following code will cause variable `temp` to be implicitly captured by the linq clause:
