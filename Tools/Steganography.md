# Tools for Steganography ──★

Actually, this is for me to refer, because I have halmeoni's memory hehe... Let's gaurr !!

### ExifTool
Always start with exiftool first !!
Reads and writes the metada for images, audio, and video files

Usage:
See if there is some data that should not belong in the metadata

> exiftool <file_name>


--- 
### Binwalk
Extract hidden data or embedded files from an image, video, or binary files

Usage:
Extract the hidden files

>binwalk -e <file_name>

---
### Steghide
Encodes or decodes data hidden within image or audio files using steganographic techniques

Usage:

>steghide extract -sf <file_name>

---
### StegCracker
Brute-force to extract hidden data from files that require password like StegHide

Usage:
When you suspect a file contains hidden data encrypted with a password, StegCracker tests all possible passwords from given wordlist.

> stegracker <file_name> <world_list>

---

### StegSeek
A lightning-fast tool for cracking passwords on files hidden with StegHide

Usage:
For larger files or complex CTF challenges, StegSeek is better than StegCracker

> stegseek <file_name> <word_list>

---
### StegSolve
Analyze images by cycling through color planes and extract hidden data

Basically, go through different layers and colours to find hidden data.

Usage: 
A PNG file that reveals hidden data text only in the blue channel's LSB layers

> java -jar stegsolve.jar

---
### Zsteg
Detect and extract hidden data from PNG and BMP files

Usage:
Scan multiple color planes and encodings

> zsteg <file_name>


---
### Zbarimg 
To read the contents of an image, such as QRCode

Usage:
> zbarimg <file_name>
---
### Audacity
A GUI-based audio editor to inspect waveforms, frequency spectrums, and reverse-engineer hidden data

---
### Sonic Visualizer
Analyze audio files to detect hidden messages or anomalies.