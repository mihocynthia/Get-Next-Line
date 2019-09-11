# 42-get_next_line

Reading data from a file descriptor.


#### Goals

* Learn about static variables.
* Gain a deeper understanding of allocations, whether they happen on the stack memory or in the heap memory, the manipulation and the life cycle of a buffer, the unexpected complexity implied in the use of one or many static variables.
* Discover that the initial state of a variable in a function can vary depending on the call of that very function.


General Instructions
------

* You must only submit two files : get_next_line.c and get_next_line.h
* If you are clever, you will use your libft. If so, submit your folder libft at the root of your repository.
* There cannot be a main function in your program.
* Do not push a Makefile.
* Your project must be written in accordance with the Norm.
* You have to handle errors carefully. In no way can your program, or in this particular case your function, quit in an unexpected manner (Segmentation fault, bus error, double free, etc).
* All heap allocated memory space must be properly freed when necessary.
* Your project cannot have memory leaks.
* You must submit a file called author containing your username followed by a ’\n’ at the root of your repository.
* If you choose to submit this project using your library libft, it is strictly FORBIDDEN to bypass the limitation of the Norm by adding some specific functions from your get_next_line. That would be considered cheating during your defence. Your get_next_line must hold in 5 functions of 25 lines max. 
* The libc functions allowed on this project are read, malloc and free.


Mandatory part
------

* Write a function that returns a line read from a file descriptor (*“line” is a succession of characters that end with ’\n’*)
* Your function must be prototyped as follow:  int get_next_line(const int fd, char **line);
  - The first parameter is the file descriptor that will be used to read.
  - The second parameter is the address of a pointer to a character that will be used to save the line read from the file descriptor.
  - The return value can be 1, 0 or -1 depending on whether a line has been read, when the reading has been completed, or if an error has happened respectively.
* Your function get_next_line must return its result without ’\n’.
* Calling your function get_next_line in a loop will then allow you to read the text available on a file descriptor one line at a time until the end of the text, no matter the size of either the text or one of its lines.
* Make sure that your function behaves well when it reads from a file, from the standard output, from a redirection etc.
* In you header file get_next_line.h you must have at least the prototype of the function get_next_line and a macro that allows to choose the size of the reading buffer for the read function. This value will be modified during the defence to evaluate the strength of your function. That macro must be named BUFF_SIZE.

Bonus part
------

* To succeed get_next_line with a single static variable.
* To be able to manage multiple file descriptor with your get_next_line. For ex- ample, if the file descriptors 3, 4 and 5 are accessible for reading, then you can call get_next_line once on 3, once on 4, once again on 3 then once on 5 etc. without losing the reading thread on each of the descriptors.
