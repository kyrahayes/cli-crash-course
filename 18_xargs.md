# Xargs

Xargs is a command to read from stdin, which is a stream of data, and convert each line into arguments that are passed to another command.

Our hello_world.sh [ex. 3](example3) took in two command line arguments like this:

```
action@cli-crash-course-197957:~$ ./hello_world.sh Jenna Pederson
```

But what if we only have a file of data? Using file redirection won't work because we are expecting command line arguments not stdin from a file.

```
action@cli-crash-course-197957:~$ ./hello_world.sh < names.txt
Hello World,  !
```

Instead we can use xargs to convert from stdin to arguments [ex. 8](example8).

```
action@cli-crash-course-197957:~$ cat names.txt | xargs ./hello_world.sh
Hello World, Jenna Pederson!
```