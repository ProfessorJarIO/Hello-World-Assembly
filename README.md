# Hello World Assembly Program
> December 23rd, 2024
---

** We are using x64 bit assembly code**

Now that I've taken a look at syscalls for Linux, I'm starting to understand what's going on. In the Linux system call table: https://blog.rchapman.org/posts/Linux_System_Call_Table_for_x86_64/, we see sys_write, or rax=1 looks for rdi, rsi, and rdx. If we want to look further in detail, check the link: https://linux.die.net/man/2/write. As specified in the man page: write() writes up to count bytes from the buffer pointed buf to the file referred to by the file descriptor fd. The `fd` or file descriptor can be `1` or `2` for standard output or standard error respectively: https://stackoverflow.com/questions/3866217/how-can-i-make-the-system-call-write-print-to-the-screen. Next, the `buf` parameter asks for a string to be printed, along with `count` that writes up to `count` bytes from the buffer. 

Note that the write function is typically used for writing data to files. However, because we are specifying in the `fd` parameter to print to STDOUT, we are actually printing to the console instead of a file descriptor.

All of this is starting to make so much more sense now :)

Look at this if you are still confused: https://electronicsreference.com/assembly-language/linux_syscalls/write/

This link is where I learned the functions for the syscalls: https://hackeradam.com/x86-64-linux-syscalls/

Check out sys_exit next and see if you can understand it too.
