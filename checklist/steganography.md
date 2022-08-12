# Steganography

## File

Just to be sure what file you are facing with, check its type with `type <filename>`

## Exif

Check all image Metadata using `Exiftool <filename>`

Useful online tool: [ExifData](https://www.exifdata.com/)

## Binwalk

Use binwalk to check image's for hidden embedded files.

**Useful Commands:**

`binwalk file` : Displays the embedded data in the given file

`binwalk -e file` : Displays and extracts the data from the given file

`binwalk -Me <filename>`. `-Me` is used to recursively extract any files.

## PNG Check

We can use `pngcheck` to look for optional/correct broken chunks. This is vital if the image appears corrupt.

Run `pngcheck -vtp7f <filename>` to view all info.

`v` is for verbose, `t` and `7` display text chunks, `p` displays contents of some other optional chunks and `f` forces continuation after major errors are encountered.

## **Found a password?**&#x20;

If you've found a password, the goto application to check should be [steghide](http://steghide.sourceforge.net/). Bear in mind that steghide can be used without a password, too.

You can extract data by running `steghide extract -sf <filename>`.

Useful online Tools:

* [OpenStego](https://www.openstego.com/)
* [Stegpy](https://github.com/Baldanos/Stegpy)
* [Outguess](https://outguess.rbcafe.com/)
* [jphide](http://linux01.gwdg.de/\~alatham/stego.html)

## Stegsolve <a href="#wavsteg" id="wavsteg"></a>

Sometimes there is a message or a text hidden in the image itself and in order to view it you need to apply some color filters or play with the color levels. \
You can get it from [github](https://github.com/eugenekolo/sec-tools/tree/master/stego/stegsolve/stegsolve)

Useful online Tool: **** [StegOnline](https://stegonline.georgeom.net/upload)

## Wavsteg <a href="#wavsteg" id="wavsteg"></a>

WavSteg is a python3 tool that can hide data and files in wav files and can also extract data from wav files.\
You can get it from [github](https://github.com/ragibson/Steganography#WavSteg)

Useful commands:\
`python3 WavSteg.py -r -s soundfile -o outputfile` : extracts data from a .wav sound file and outputs the data into a new file

## Sonic visualizer <a href="#sonic-visualizer" id="sonic-visualizer"></a>

Sonic visualizer is a tool for viewing and analyzing the contents of audio files, however it can be helpful when dealing with audio steganography. You can reveal hidden shapes in audio files.\
[Offical Website](https://www.sonicvisualiser.org/)

## Bruteforce

### [StegCracker](https://github.com/Paradoxis/StegCracker) <a href="#stegcracker" id="stegcracker"></a>

A tool that bruteforces passwords using `steghide`

### Fcrackzip <a href="#fcrackzip" id="fcrackzip"></a>

Sometimes the extracted data is a password protected zip , this tool bruteforces zip archives.\
It can be installed with `apt` however the [source](https://github.com/hyc/fcrackzip) can be found on github.\


**Useful commands:**\
`fcrackzip -u -D -p wordlist.txt <filename.zip>` : bruteforces the given zip file with passwords from the given wordlist



