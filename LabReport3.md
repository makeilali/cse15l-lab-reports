# Part 1
- Failure-inducing input
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
  @Test
  public void testReversed() {
    int[] input1 = { 1, 2, 3, 4 };
    assertArrayEquals(new int[]{ 4, 3, 2, 1 }, ArrayExamples.reversed(input1));
  }
```
- Non-Failing
  ```
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
  @Test
  public void testReverseInPlace() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
	}
  ```
- The Symptom
  
![image](https://github.com/makeilali/cse15l-lab-reports/blob/main/Screenshot%202024-02-13%20153331.png?raw=true)

- Before code change
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```
- After code change
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
```
-The fix in the code helped adrress the issue in why the the test case was failing is because the code was trying to reverse the ```newArray``` rather than the ```arr```. So after making the change the code would reverse the original ```arr``` into the ```newArray``` and return the ```newArray``` instead of the original ```arr```, which allowed for the test cases to pass.
# Part 2
## '-name'
- Example 1
```
[user@sahara ~/docsearch-main]$ find ./technical -name "*1-1.txt"
./technical/biomed/1471-2466-1-1.txt
./technical/biomed/1471-2148-1-1.txt
./technical/biomed/1475-2832-1-1.txt
./technical/biomed/1471-2202-1-1.txt
./technical/biomed/1471-2172-1-1.txt
./technical/biomed/1472-6769-1-1.txt
./technical/biomed/1472-6807-1-1.txt
./technical/biomed/1471-2105-1-1.txt
./technical/biomed/1471-213X-1-1.txt
./technical/biomed/1471-2253-1-1.txt
```
- This example uses the ```find``` command to find any file that ends in ```1-1.txt```. 
- Example 2
```
[user@sahara ~]$ find ./docsearch-main/technical -name "*.log"
```
- This example uses the ```find``` command to find any file that ends in ```.log``` there was no output because the doc search only had ```.txt``` files thuis resulting in this output. 
## '-type'
- Example 3
```
[user@sahara ~]$ find ./docsearch-main/technical -type d
./docsearch-main/technical
./docsearch-main/technical/911report
./docsearch-main/technical/biomed
```
- This example shows the ```-type``` command which allows to find all the directories in ```./technical```
- Example 4
```
[user@sahara ~]$ find ./docsearch-main/technical -type f
./docsearch-main/technical/biomed/1471-2199-3-7.txt
./docsearch-main/technical/biomed/1471-2121-1-2.txt
./docsearch-main/technical/biomed/1471-2164-3-10.txt
./docsearch-main/technical/biomed/1471-2407-2-9.txt
./docsearch-main/technical/biomed/1471-2210-1-7.txt
./docsearch-main/technical/biomed/1472-6882-1-11.txt
./docsearch-main/technical/find-results.txt
... many more files ...
```
- This example shows the ```-type``` command which allows to find all the files in ```./technical```
## '-mtime'
- Example 5
```
find ./docsearch-main/technical -mtime -1
./docsearch-main/technical/biomed/1471-2199-3-7.txt
./docsearch-main/technical/biomed/1471-2121-1-2.txt
./docsearch-main/technical/biomed/1471-2164-3-10.txt
./docsearch-main/technical/biomed/1471-2407-2-9.txt
./docsearch-main/technical/biomed/1471-2210-1-7.txt
./docsearch-main/technical/biomed/1472-6882-1-11.txt
./docsearch-main/technical/find-results.txt
... many more files ...
```
This example shows the ```-mtime``` which checks modification time as this example shows all the documents modifed in the last 24 hours as this may be because of it being downloaded to another computer than the original.
- Example 6
```
[user@sahara ~]$ find ./docsearch-main/technical -mtime +365
```
This example shows the ```-mtime``` which checks modification time as this example shows all the documents modifed in the last year as none have been modified.
## '-size'
- Example 7
```
[user@sahara ~]$ find ./docsearch-main/technical -size +5M
```
This example shows if a file is larger than 5MB. None
- Example 8
```
[user@sahara ~]$ find ./docsearch-main/technical -size -1k
./docsearch-main/technical/find-results.txt
```
This example shows if a file is less than 1K. 
## Citing
This allowed me to use the terminal to accesss different directories or files in the docsearch using the find commmand.
I changed the output accordingly to the examples I had to write that helped learn and understanding of what the commmand was doing.

I asked ChatGpt what are different command line output using find?
Output:
The find command in Unix and Unix-like operating systems is highly versatile, allowing users to locate files and directories based on a wide array of criteria like name, type, size, modification date, and more. The output of the find command can vary significantly depending on the options and expressions used. Here are some different outputs you might see with various uses of find:

1. Basic Find by Name
Command: find /path/to/search -name "filename.txt"
Output: Lists the path(s) to any files named filename.txt within the specified directory tree.
2. Find by Type
Command: find /path/to/search -type d
Output: Lists all directories (d) within the specified path, one per line.
3. Find by Modification Time
Command: find /path/to/search -mtime -7
Output: Lists all files modified in the last 7 days.
4. Find and Execute a Command
Command: find /path/to/search -type f -exec grep "searchText" {} \;
Output: For each file (f) found, executes grep looking for "searchText". Outputs the lines containing "searchText" prefixed with the file name.
5. Find with Depth Limit
Command: find /path/to/search -maxdepth 1 -name "*.txt"
Output: Lists .txt files located directly within the specified directory, not diving into subdirectories due to -maxdepth 1.
6. Find Inverting Match
Command: find /path/to/search -not -name "*.txt"
Output: Lists all files and directories that don't end in .txt.
7. Find by Permissions
Command: find /path/to/search -perm 644
Output: Lists files with permissions set to 644.
8. Find by Size
Command: find /path/to/search -size +10M
Output: Lists files larger than 10 megabytes.
9. Find and Delete
Command: find /path/to/search -name "*.tmp" -delete
Output: This command doesn't output a list but will delete all .tmp files found. Use with caution.
10. Find with Logical Operators
Command: find /path/to/search \( -name "*.tmp" -o -name "*.log" \)
Output: Lists files ending in .tmp or .log, demonstrating the use of logical OR (-o) with grouped expressions.
