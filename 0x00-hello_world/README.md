Resources: <br>

https://en.wikipedia.org/wiki/Dennis_Ritchie<br>
https://www.youtube.com/watch?v=de2Hsvxaf8M&ab_channel=Computerphile<br>
https://www.youtube.com/watch?v=smGalmxPVYc&ab_channel=ChrisHawkes<br>
https://www.youtube.com/watch?v=rk2fK2IIiiQ&ab_channel=JonathanEngelsma<br>
https://www.youtube.com/watch?v=FwpP_MsZWnU&ab_channel=JonathanEngelsma<br>
https://www.youtube.com/watch?v=VDslRumKvRA&ab_channel=HowTo<br>
https://github.com/holbertonschool/Betty/wiki<br>
http://harmful.cat-v.org/software/c++/linus<br>
https://twitter.com/unix_byte/status/1024147947393495040?s=21<br>

<h2>Quiz</h2>

<h2>Scripts</h2>

<ol>
<li>[0. Preprocessor<br>

Write a script that runs a C file through the preprocessor and save the result into another file.<br>

The C file name will be saved in the variable $CFILE<br>
The output should be saved in the file c<br>

#!/bin/bash<br>
gcc -E $CFILE -o c

<li>[1. Compiler<br>

Write a script that compiles a C file but does not link.<br>

The C file name will be saved in the variable $CFILE<br>
The output file should be named the same as the C file, but with the extension .o instead of .c.<br>
Example: if the C file is main.c, the output file should be main.o<br>

#!/bin/bash<br>
gcc $CFILE -c<br>

</ol>