# Lab Report 1
January 10, 2024 <br/>
**Terminal Commands:**
We learned to use `cd`, `cat`, `ls`, and `pwd`. <br/>

---
`cd` changes the directory that you are in, taking an input of the file destination that you want to go to.
```
[user@sahara ~/lecture1]$ cd
[user@sahara ~]$
```
Without an input, `cd` by default will revert back to the original directory, in this case being `~`. <br/>
```
[user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$ 
```
With a directory input, the command will take you to that directory, in this case being `~/lecture1`. <br/>
```
[user@sahara ~/lecture1]$ cd README
bash: cd: README: Not a directory
[user@sahara ~/lecture1]$
```
With a file input, the command will return an error, because the terminal cannot travel to a file location, only to a directory. `~/lecture1/README` is a file within `~/lecture1`, but there are no other files within it so the terminal cannot travel there(example above). <br/>

---
`cat` concatenates two inputs together, and returns the result. <br/>
```
[user@sahara ~/lecture1]$ cat
```
Without an input, `cat` breaks the terminal and doesn't allow you to type in anymore commands. <br/>
```
[user@sahara ~/lecture1]$ cat messages 
cat: messages: Is a directory
```
With a directory input, such as `~/lecture1/README`, the command will return an error, because it cannot concatenate a directory with another file. <br/>
```
[user@sahara ~/lecture1]$ cat README messages/en-us.txt
To use this program:

javac Hello.java
java Hello messages/en-us.txt
Hello World!
```
With a file input, the command will return the text within the file, and with two file inputs, the terminal will print them one after another, in this case printing the README file first, and then the en-us.txt file. <br/>

---
`ls` lists the files of a directory
```
[user@sahara ~/lecture1]$ ls
Hello.class  Hello.java  messages  README
```
Without an input, `ls` lists the files of the directory that the terminal is currently in. In the example above, the current terminal is `~/lecture1` and it lists out the four possible paths, `~/lecture1/Hello.class`  `~/lecture1/Hello.java`  `~/lecture1/messages`  `~/lecture1/README`. <br/>
```
[user@sahara ~/lecture1]$ ls messages
en-us.txt  es-mx.txt  th.txt  zh-cn.txt
```
With a directory input, `ls` lists the files within that directory. In the example above, the current terminal is `~/lecture1` but we ask the terminal to list the files within the `~/lecture1/messages` directory. It then lists the four possible paths from `~/lecture1/messages`, those being `~/lecture1/messages/en-us.txt`,  `~/lecture1/messages/es-mx.txt`,  `~/lecture1/messages/th.txt`, and  `~/lecture1/messages/zh-cn.txt`. One thing to take note of is that we can only `ls` from a file or directory WITHIN our current directory, not just anything.  <br/>
```
[user@sahara ~/lecture1]$ ls README
README
```
With a file input, `ls` will just list the name of that file, and return it. The current terminal is `~/lecture1`, and we are accessing the `README` file. Once again, this file must be within the current directory. <br/>

---
`pwd` displays the current directory that you are in, regardless of input. In this case, the current directory is `~/lecture1` or `/home/lecture1`.
```
[user@sahara ~/lecture1]$ pwd
/home/lecture1
```
