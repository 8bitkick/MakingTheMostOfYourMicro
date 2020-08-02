# MakingTheMostOfYourMicro
A BBC BASIC program was transmitted over audio at the end of the BBC television program [Making The Most Of Your Micro Episode 10](https://youtu.be/SvF2fW8KBcA?t=1368).

The computer 'cassette' audio is in this repo as a [WAV](https://github.com/8bitkick/MakingTheMostOfYourMicro/blob/master/micro.wav)

Data was retreived from the WAV using the following command HT [@m0rb](https://twitter.com/m0rb/status/1289774206712872960?s=20)
~~~
minimodem -r -f micro-mono.wav -M 2400 -S 1200 -R 44100 300 > micro.bin
~~~


## Transmitted data

The text of the message is readble directly, although includes BBC BASIC keywords encoded as byte tokens which are outside of printable range. The data also includes the headers and CRC bytes of the [Acorn Cassette Format](http://beebwiki.mdfs.net/Acorn_cassette_format).

The audio contains a single BASIC program titled `MESSAGE`


~~~
*MESSAGE
22,7
l=0 
 23:
132,157,131,10,8,8,8:
132,157,131
28,3,24,37,0
(12);"PO.BOX 7, LONDON W3 6XJ";
"Dear Viewer,"';
(4);"If you've been watching Making the Most of the Micro we'd be glad to have your reactions,good or bad and an idea of
X*MESSAGE
dX the kind of  things you'd like to see in future series.";
"Drop us a line. Mark your envelope MTMOTM on the top left hand corner."
(4);"And if you'd  like to submit a question  which  might be answered in the live  special  programme in October , pleaZ
*MESSAGE
se  send  it  on   a"
"postcard, including  your  address and   telephone   number .  Please indicate if you  would be happy to be phoned in  connection with this live programme or would like to be considered for the studio audience.";
"With   seves
*MESSAGE
R+ral   thousand  letters arriving each  week we hope you'll forgive us if we don't acknowledge your letter."'
(4)"Best Wishes,"'
(6);"Mac and the Production Team";
~~~

## Running the program

The audio either needs to be run through MakeUEF to create a UEF file playable on an emulator like JSbeeb, or the [binary data](https://github.com/8bitkick/MakingTheMostOfYourMicro/blob/master/micro.bin) in this repo manually stripped of the Acorn Cassette Format encoding so that the BASIC program can be loaded directly into memory. TBD

