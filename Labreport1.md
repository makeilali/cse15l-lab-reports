# cd examples
## Image 1
![Image](https://github.com/makeilali/cse15l-lab-reports/blob/main/Screenshot%202024-01-16%20at%205.05.59%20PM.png?raw=true)
- The working directory was [user@sahara ~]$.
- With no arguments the terminal didn't produce an output because we were in a directory already.
- No error
## Image 2
![Image](https://github.com/makeilali/cse15l-lab-reports/blob/main/Screenshot%202024-01-16%20at%205.51.57%20PM.png?raw=true)
- The working directory was [user@sahara ~/lecture1]$
- Cd used in the terminal with the argument lecture1 changed the directory into [user@sahara ~/lecture1]$.
- No error
## Image 3
![Image](https://github.com/makeilali/cse15l-lab-reports/blob/main/Screenshot%202024-01-16%20at%206.01.44%20PM.png?raw=true)
- The working directory was [user@sahara ~/lecture1]$
- This was the output because cd was used with Hello.java which is not a directory, but a file which caused this output.
- This is an error because cd uses directories, while Hello.java was a file

# ls examples
## Image 1
![Image](https://github.com/makeilali/cse15l-lab-reports/blob/main/Screenshot%202024-01-16%20at%205.06.05%20PM.png?raw=true)
- The working directory was [user@sahara ~]$
- This was the output because the command put in the terminal had no arguments for any files to be listed.
- no error
## Image 2
![Image](https://github.com/makeilali/cse15l-lab-reports/blob/main/Screenshot%202024-01-16%20at%205.51.50%20PM.png?raw=true)
- The working directory was [user@sahara ~]$
- This was the output because the command put in the terminal asked to list the files of lecture1 which resulted in the output.
- no error
## Image 3
![Image](https://github.com/makeilali/cse15l-lab-reports/blob/main/Screenshot%202024-01-16%20at%206.01.20%20PM.png?raw=true)
- THe working directory was [user@sahara ~/lecture1]$
- This was the output becasue the file Hello.java had no files to be listed so it returned the input of file Hello.Java.
- no error 
# cat examples
## Image 1
![Image](https://github.com/makeilali/cse15l-lab-reports/blob/main/Screenshot%202024-01-16%20at%205.06.13%20PM.png?raw=true)
- The working directory was [user@sahara ~/lecture1]$
- This was the output because the command put in the terminal had no arguments for any files to be read.
- no error
## Image 2
![Image](https://github.com/makeilali/cse15l-lab-reports/blob/main/Screenshot%202024-01-10%20at%201.48.09%20PM.png?raw=true)
- The working directory was [user@sahara ~/lecture1]$
- This was the output because when written in the terminal "cat Hello.java" this allows for the cat command to read what is in the Hello.java file and writes it as a output
- no error
## Image 3
![Image](https://github.com/makeilali/cse15l-lab-reports/blob/main/Screenshot%202024-01-16%20at%205.51.08%20PM.png?raw=true)
- The working directory was [user@sahara ~]$
- This was output because the terminanl was trying to read lecture 1 as a file rather it was a directory resulting in this output.
- Yes an error occured because the command cat reads files and not directories and in this case lecture1 is a directory.
