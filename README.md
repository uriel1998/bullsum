# bullsum
Using the Corporate Bull**** Generator as a lorem ipsum generator


This is a bash script to use the [Corporate BullShit Generator](https://sourceforge.net/projects/cbsg/) as a lorem ipsum generator for the commandline.

# Requires

* curl
* grep
* sed
* awk

# Usage

If you just want one line (NOT one sentence) only all the time, use this one-liner instead:

```
curl -s https://cbsg.sourceforge.io/cgi-bin/live | grep -Eo '^<li>.*</li>' | sed s,\</\\?li\>,,g | shuf -n 1 
```
bullshit -l [ -p # | -s #]  
-l Begin with  Lorem ipsum dolor sit amet, consectetur adipiscing elit.  
-s Specify number of sentences.   
-p Specify number of paragraphs.  
   Paragraphs are *always* five sentences each.  
-h shows this help message  

# Advanced Usage

To get the output into the clipboard, use  
```
| tee >(xclip -selection primary) >(xclip -selection secondary) >(xclip -selection clipboard)
```
or
```
| tee >(xsel -i --primary) >(xsel -i --secondary) >(xsel -i --clipboard)
```
