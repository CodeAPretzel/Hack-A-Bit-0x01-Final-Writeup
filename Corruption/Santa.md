## Challenge ~
You all asked for it so here it is, an intro to binary exploitation!

Let's get started nice and simple, baby steps to reverse engineering (RE).

All challenges in this section use the same binary. The target is x86 and ASLR is on but it shouldn't be relevant to any of your exploits.
<br>
- [Corruption](../Assets/Downloadable/corruption)

## Solution ~
Another easy one, maybe not at first glance though. This entire section of corruption is about reverse engineering; getting into the core of code and finding out what's inside. 
<br>
So, in order to solve this one, we have two options: <b>1.</b> read the code raw to see if there is anything in there in plaintext or <b>2.</b> use your favorite decompiler tool to reorganize through the mess and find what you can. In my first run of this, I decided to do the first option and, after some sifting, found the flag covered in plaintext.

<br>
<img src="" alt="Flag bro...">
</br>

After doing a re-run of this, I should have used grep but forgot that the flag would have been in <i>flag format</i>, but I guess that's my fault :P
<br>
<b>🚩 flag{baby_steps_gift_just_for_you}</b>

## Defense ~
This challenge can be protected through some methods, however, people would still be able to read and decipher the code piece in the end. In a lovely <a href="https://stackoverflow.com/questions/6481668/protecting-executable-from-reverse-engineering">StackOverflow article</a>, scripts can be protected by "obfuscating" your code from disassemblers and other tools. Those techniques I am unsure what they might be, however, computers have to find a way to decipher your code in order to run it. Eventually, someone will be able to find out how the computer runs the program. After that, <i>it's game over!</i> ☠️
