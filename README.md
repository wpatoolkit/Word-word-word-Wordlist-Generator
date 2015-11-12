# Word-Word-Word Wordlist Generator 
This is a small program written in C++ that will output combinations of 3 to 5 length words in the format...<br>

`word-word-word`<br>

It includes a built-in dictionary of:

`454 3-letter words`<br>
`1,400 4-letter words`<br>
`2,225 5-letter words`<br>

By default it will combine words in these formats:

`5-3-4`<br>
`5-4-3`<br>
`4-3-5`<br>
`4-5-3`<br>
`3-4-5`<br>
`3-5-4`<br>

Using the `-full` switch will cause it to output combinations in these additional formats:

`3-3-4`<br>
`3-3-5`<br>
`3-4-3`<br>
`3-4-4`<br>
`3-5-3`<br>
`4-3-3`<br>
`4-4-3`<br>
`5-3-3`<br>

To compile on Windows (requires the <a href="http://www.microsoft.com/en-us/download/details.aspx?id=8279">Windows 7 SDK</a>):<br>
`cl /EHsc ee.cpp`

To compile on Linux:<br>
`g++ ee.cpp -oee`

##Example usage:
`ee | oclHashcat64 -m 2500 CAP.hccap`<br>
pipes its output into <a href="http://hashcat.net/oclhashcat/">oclHashcat</a> (AMD)

`ee | cudaHashcat64 -m 2500 CAP.hccap`<br>
pipes its output into <a href="http://hashcat.net/oclhashcat/">cudaHashcat</a> (NVIDIA)

`ee | aircrack-ng -w - CAP.cap -e SSID`<br>
pipes its output into <a href="http://www.aircrack-ng.org/">aircrack-ng</a>

`./ee | pyrit -r CAP.cap -i- attack_passthrough`<br>
pipes its output into <a href="https://code.google.com/p/pyrit/">pyrit</a>

## Parameters
`-full`<br>
Uses a more comprehensive set of combinations.

By default 8,485,260,000 combinations are generated (approx ~160GB in wordlist form).

If you use the `-full` switch 12,506,451,500 combinations are generated (approx ~200GB in wordlist form).
