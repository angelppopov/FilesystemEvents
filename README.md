# FilesystemEvents
Monitoring filesystem events
# Notification
The  C program shows a simple demo Inotify application, which watches a directory for file and directory creation, modification and deletion events.

gcc -o notification notification.c

./notification /folder/path

# Watching subdirectories
The C program does the above, traversing only the subdirectories immediately under the specified directory, using functions from dirent.h, and adds a watch for each. Subsequently, instead of printing events directly to stdout, it logs it into a file, inotify_logger.log.


# Auto Compile
Now that you have a basic idea of how you can use Inotify in applications that may need to monitor the filesystem, let us do something fun, and possibly, quite useful. Using Inotify, let us monitor a directory, and whenever a C source file is created or modified in it, let’s invoke gcc to compile the file automatically, and place the binaries in a separate bin/ directory under this directory.

$ gcc auto_compile.c 

$ ./a.out /home/gene/codes/ 

Watching:: /home/gene/codes/ 

Compiling:: hello1.c 

Compiling:: hello2.c
