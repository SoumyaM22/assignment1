# assignment1
Linux system calls and Library functions

The programming task requires you to create a utility to traverse a specified directory in breadth-first order. Breadth-first search
explores all the nodes at a given level before descending lower in the tree. Breadth-first search is implemented with a queue.
As the program encounters each directory node at a particular level, it enqueues the pathname for later examination. You can
use the following pseudocode which makes use of queue ADT. You will have to provide the code for queue ADT operations
yourself.
breadthfirst ( root )
{
enqueue ( root );
while ( ! empty ( queue ) )
{
next = dequeue ( queue );
for each node directly below next
{
visit ( node );
if ( isa_directory ( node ) )
enqueue ( node );
}
}
}
The indentation of the filenames shows the level in the file system tree. Use the output format specified in Example 5.37, with
a default indentation of 4 spaces for each level in the directory. You should be able to change the indentation spaces by using
an option on command line followed by a number. The executable should be called bt. The program will be invoked by:
bt [-h] [-L -d -g -i -p -s -t -u -In | -l] [dirname]
The options are to be interpreted as follows:
h Print a help message and exit.
L Follow symbolic links, if any. Default will be to not follow symbolic links.
t Print information on file type.
p Print permission bits as rwxrwxrwx.
i Print the number of links to file in inode table.
I n Indent by n spaces.
Linux System Calls 2
u Print the UID associated with the file.
g Print the GID associated with the file.
s Print the size of file in bytes. If the size is larger than 1K, indicate the size in KB with a suffix K; if the size is larger than
1M, indicate the size in MB with a suffix M; if the size is larger than 1G, indicate the size in GB with a suffix G.
d Show the time of last modification.
l This option will be used to print information on the file as if the options tpiugs are all specified.
