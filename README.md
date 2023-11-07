# CS 212: Project 1B

Assignment: Create a script that will create a directory structure, and files within that directory structure, all with the specified file permissions. The files should contain the specified contents. The script should be named “proj1B” exactly. (A consistent name will help with grading.)  

Note: you are only allowed to use the following commands: cd, chmod, cp, echo, mkdir, mv, rm, rmdir, touch. (You do not need to use all of these commands to complete the assignment successfully.) 

This is the directory structure you should make:

![image](https://github.com/ms126/proj1B/assets/109988475/5422d08e-7f7d-4659-b837-41af207e5f7f)

The script should take an argument, and the argument should be the location to create the directory. So, if the script is run as “bash proj1b tmp” then the script would create directories tmp, tmp/dir1, tmp/dir2, etc., and files tmp/dir1/fileA, tmp/dir2/fileB, etc. Assume that all operations are relative to the current directory (no absolute paths like ~ or /tmp). Note: please don’t write this in the overall root directory (i.e., “/”). In effect, the “Root dir” box should be named the same as the argument to the script. 

Use the proj1B_checker Download proj1B_checkerscript to check your work as follows: first, run your script with an argument, “bash proj1B tmp” (for example). Then, run the checker script with the same argument, “bash proj1B_checker tmp” for example. The checker script will echo a congratulatory message if it thinks your work is satisfactory. 

What to turn in? One file: proj1B (your script). 

One last thing: it will probably take at least a few tries to get your script right.  When you create dir3 with permissions 000, it can be tricky to remove.  Here is how I did it:

bash ./proj1B tmp
bash ./proj1B_checker tmp # this script told me I had a failure
chmod -R 755 tmp  # recursively changes permissions to something that can be read and written over (i.e., deleted)
rm -Rf tmp # deletes "tmp" and everything within tmp (recursive) ... be careful with this ... once you delete something in Unix, it is gone forever

and then started the cycle over again.

 

A final note: those of you familiar with Unix may be aware of "sudo" which lets you bypass various permission issues.  Your script should not require sudo.  If you feel like you need sudo, then I encourage you to rethink the sequence of operations you are doing.



