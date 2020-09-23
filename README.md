<div align="center">

## lcfind


</div>

### Description

This program allows you to find a file or a directory in a specified drive (e.g. your hard disk, a floppy, your cd-rom...). It search for it in all the directories you have in that drive. Click Luke to go to my Web Page: other source code available...
 
### More Info
 
You have to input the drive (i.e. 'c' or 'a' or 'd' or whatever else) and the name (or part of it) of the file or directory you're searching for.

This program return the path of all the files (or directories) found in that drive.


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Luke](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/luke.md)
**Level**          |Beginner
**User Rating**    |3.8 (15 globes from 4 users)
**Compatibility**  |C
**Category**       |[Files](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/files__3-2.md)
**World**          |[C / C\+\+](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/c-c.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/luke-lcfind__3-492/archive/master.zip)





### Source Code

```
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
main(int argc, char *argv[])
{
 char *instruction;
 if (argc != 3)
 {
 printf("\nUsage is: lcfind drive name\n\n");
 printf(" drive: it is the drive in which you want\n");
 printf("  to search for your file or directory.\n");
 printf(" name : it is the name of the file (or part of\n");
 printf("  the name) or of the directory that you\n");
 printf("  are searching for.\n\n");
 printf("Example: lcfind c lcfind\n");
 return -1;
 }
 instruction = calloc(101, sizeof(char));
 strcat(instruction, "dir ");
 strcat(instruction, argv[1]);
 strcat(instruction, ":\\");
 strcat(instruction, "*");
 strcat(instruction, argv[2]);
 strcat(instruction, "* /s /l /b | more");
 system(instruction);
 return 0;
}
```

