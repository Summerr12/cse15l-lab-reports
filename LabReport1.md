## Benjamin Nhan, 
## CSE15L
---
## **cd**

- **No arguments:**

![Image](cd1.png)

*The working directory was previously on `\home` which looks like [user@sa  hara ~]$ in the terminal*

When I used `cd`, nothing changed because I was "change directory" to the default root directory "~".
Since there are no arguments in `cd` yet, we are returned to the same spot.
The output isn't an error because I was given a new line to write again with `\home`.

- **Path to directory:**

![Image](cd2.png)

*The working directory was previously on `\home`*

When I used `cd lecture1` which is adding a directory in the argument of `cd`, the code didn't change anything in the file but changed my location in the terminal. so it became [user@sahara ~/lecture1]$ because I was continously delivered to lecture. Now if I type `ls`, I can see all the files within `lecture1`.
The output isn't a error because I was given a fresh command line saying user@sahara ~/lecture1]$ which is `\home\lecture1`

- **Path to a file:**

![Image](cd.png)

*The working directory was previously on `\home\lecture1\messages`*

When I used `cd ja.txt`, I didn't move anywhere and was given an error message saying `ja.txt` wasn't a directory. So the directory stayed the same.
The output is an error because there was a red popup and it didn't move me anywhere in the directory because I wasn't moving toward a directory but a file in the first place.

---

## **ls**

- **No argument:**

![Image](ls1.png)

*The working directory was previously on `\home`*

The output of `ls` was only `lecture1` because it had no arguments, it only gave the face value list of the current directory or what is seen first on the workspace.
There is no output error because we can always `ls` to see what files are available to `cd` into next.

- **Path to directory**:

![Image](ls3.png)

*The working directory was previously on `\home`*

The output of `ls messages` which is toward a file doesn't work because we are currently at the default home directory. This output is a error because we cannot skip the first directory being `lecture1`. Hence the new output is `ls lecture1/messages` which allows a direct path to messages outputing `en-us.txt`  `es-mx.txt`  `ja.txt`  `zh-cn.txt`. This version has no output error since it returns text file names and sends back the default command prompt and root directory.

- **Path to a file:**

![Image](ls4.png)

*The working directory was previously on `\home`*

The output of `ls lecture1/messages/en-us.txt` is towards a file and produces the name of our path. I believe because there is no content or paths left inside the file. This has no output error because it returns the default command prompt and root directory.

---

## **cat**

- **No argument:**

![Image](cat1.png)

*The working directory was previously on `\home`*

The `cat` command alongisde no arguments reads data/input from the user and write it back as output. Although it continues as long as you type, it doesn't stop the command, it is not an error output because there is no error signal either. You can end the command through `control + c` and return it to standard directory prompt

- **Path to directory:**

![Image](cat2.png)

*The working directory was previously on `\home`*

The output of `cat lecture1` is "cat: lecture1: Is a directory". This is not an error output because it produced the fact that it wasn't a file.

![Image](cat3.png)

*The working directory was previously on `\home`*

The output of `cat lecture1/messages` is "cat: lecture1/messages: Is a directory." This is not an error output because it produced the fact that it wasn't a file.

- **Path to a file:**

![Image](cat3.5.png)

*The working directory was previously on `\home`*

The output of `cat lecture1/messages/ja.txt` is what I put in the text file for japanese translation for "Hello world!" "「こんにちは世界」". This is not an error output because the cat concatenated the ja file and printed the correct words.
