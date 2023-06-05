## Challenge ~
With access to `10.128.0.5` your goal is to escelate priveleges to the `breakme-harder` user. Ultimately your goal is simply to read out the flag in `/home/breakme-harder/`.
<br>

`range.final.hackabit.com`

<br>

<div align="center">
  <b>IMPORTANT -- CHALLENGES IN RANGE WILL BE LESS DESCRIPTIVE SINCE THE MACHINES HOSTING THE CHALLENGES ARE DOWN</b>
</div>
    
<br>
<br>
    
## Solution ~
From the previous challenge `Rightface`, we are still in the shell and are told to read a text file in the directory of the `breakme-harder` user. Using just cat will not work because we don't have the premissions to do so. Instead, we look at the files given to us in the `breakme` user:

```
-$ ls -l

## Looks something like:

escalator
escalator.c
flag.txt
```

The <i>C</i> script `escalator.c` seems interesting. Upon further investigation into the file we get:

```c
#include <stdio.h>

int main(int argc, char *argv[]) {
    FILE *file;
    char ch;

    // Check if a filename argument is provided
    if (argc < 2) { return 1; }

    // Open the file in read mode
    file = fopen(argv[1], "r");
  
    // Check if the file was opened successfully
    if (file == NULL) {
        printf("An error occured.\n");
        return 1;
    }

    // Read and print each character from the file
    while ((ch = fgetc(file)) != EOF) {
        putchar(ch);
    }

    // Close the file
    fclose(file);

    return 0;
}
```

Apparently the script takes the argument of a file and displays the contents. Also, told to me by another competitor, this file's SUID is owned by `breakme-harder` meaning that running this would be like `breakme-harder` is running this. Now all we have to do is run the file and have the file as the argument:

```
-$ ./escalator /home/breakme-harder/flag.txt
-$ flag{evaluate_this_my_dude}
```

<br>
<br>

## Final Notes ~
I would have done the last challenge `Aboutface` and the `King of the Hill` parts as well, however the KOTH was on the host of `Aboutface` and that shutdown in a little bit over a day into the competition. I would have, and should have, done the KOTH sooner but I was too focused on the other challenges. Funny enough, the main reason why no one was able to get back into the main servers is because one of the competitors ran a <a href="https://en.wikipedia.org/wiki/Fork_bomb">FORKBOMB</a> 💀 on the server at the end of the competition. However, it was funny and was awesome to see something burn and fall apart in the end, like fireworks or something. All in all, this competition was a blast and can't wait for 0x02!
