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
- Example 2
```
[user@sahara ~]$ find ./docsearch-main/technical -name "*.log"
```
## '-type'
- Example 3
```
[user@sahara ~]$ find ./docsearch-main/technical -type d
./docsearch-main/technical
./docsearch-main/technical/911report
./docsearch-main/technical/biomed
```
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
- Example 6
```
[user@sahara ~]$ find ./docsearch-main/technical -mtime +365
```
## '-size'
- Example 7
- Example 8
