# Bandit
This repo serves as my viewpoint of going through OverTheWire:Bandit CTF
This is not the best solution but merely what I did when going through.
Consider trying the challenge yourself first and enjoy the process instead of spoiling.

Level 0-1:
ssh bandit0 bandit.labs.overthewire.org -p 2220




Level 1-2:
How to open files with special characters???
Used python to do this as python was installed.
The - charcter causes the terminal to wait for furthur input so cannot use it with general commands.
User does not have permission to write files.

python was installed on the system so used the python shell to open the file and dump contents
command set:
python3
>>>f = open("file name with path","r") #r is read mode
>>>print(f.read())

To exit vim without saving changes go to normal mode first by clicking esc, then typing :q!




Level 2-3:
used the same above method here :)




Level 3-4:
File is hidden.

How to find it?
ls gives nothing, ls -l gives total 0

How to do it?
Trying to ls from outside the directory

find inhere/ gives the file names

Now just cat the file name. directly "cat"-ing with the file name will not give output and will show no such file or directory.
So we have to use the output of the find command into as a parameter for the cat command we do it by backticks `
So the command is cat `find inhere/`




Level 4-5
The password for the next level is stored in the only human-readable file in the inhere directory.
Had to do this in the same way as before using python but this was a little more work as there is no permission to create scripts




Level 5-6
This one has many files and the properties of the file is given so will need to check the properties one by one.

Need to know how to view file sizes
maybe use du command
no file seems to have a size of 1033 bytes but maybehere10 has the lowest size of 28426 so checking that first.
The above size was for directories not the files.

Have to check each folder with python script - this will give gibberish output.
Have to check how to pass files having special character to du command

Only two files in each directory seem to be not executable -file2 and spaces file2
One possiblity is checking inside each file but that will take too long. need to find the size of each one of these files. -file2 is creating problems with commands. can use to avoid - getting detected with -- after the command name followed by the argument.
had to go through all the directories manually and looking into properties of -file2 and spaces file2 till found
** had to use the -- operator to pass arguments effectively



