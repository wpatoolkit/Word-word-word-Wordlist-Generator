# Word-Word-Word Wordlist Generator 
This is a small program written in C++ that will output combinations of 3 to 5 length words in the format...<br>

`word-word-word`<br>

It includes a built-in dictionary of:

`454 3-letter words`<br>
`1400 4-letter words`<br>
`2226 5-letter words`<br>

By default it will combine words in these formats:

`3-4-5`<br>
`4-3-5`<br>
`3-5-4`<br>
`5-3-4`<br>
`4-5-3`<br>
`5-4-3`<br>

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

`-6lists`<br>
Creates 6 helper wordlists (3-4_4-3.txt, 3-5_5-3.txt, 3-norm.txt, 4-5_5-4.txt, 4-norm.txt, 5-norm.txt) for use with hashcat combinator attack...

`oclHashcat64 -m 2500 -a 1 -j "$-" ee.hccap "3-4_4-3.txt" "5-norm.txt"`<br>
`oclHashcat64 -m 2500 -a 1 -j "$-" ee.hccap "3-5_5-3.txt" "4-norm.txt"`<br>
`oclHashcat64 -m 2500 -a 1 -j "$-" ee.hccap "4-5_5-4.txt" "3-norm.txt"`<br>

By default 8,485,260,000 combinations are generated (126 GB in wordlist form).

If you use the `-full` switch 12,506,451,500 combinations are generated (181 GB in wordlist form).
