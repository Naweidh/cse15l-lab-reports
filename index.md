##Part 1 - Bugs

#A failure-inducing input for the buggy program, as a JUnit test and any associated code (write it as a code block in Markdown):
```
import static org.junit.Assert.*;
import org.junit.*;

public class ArrayTests {
	@Test 
	public void testReverseInPlace() {
    int[] input1 = { 3, 5, 15 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 15, 5, 3 }, input1);
	}


  @Test
  public void testReversed() {
    int[] input1 = { 1, 2, 3 };
    assertArrayEquals(new int[]{ 3, 2, 1 }, ArrayExamples.reversed(input1));
  }
}
```

#An input that doesn’t induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown):
```
import static org.junit.Assert.*;
import org.junit.*;

public class ArrayTests {
	@Test 
	public void testReverseInPlace() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
	}


  @Test
  public void testReversed() {
    int[] input1 = { };
    assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));
  }
}
```

#The symptom, as the output of running the tests (provide it as a screenshot of running JUnit with at least the two inputs above):
![Screen Shot 2023-11-05 at 4 40 56 PM](https://github.com/Naweidh/cse15l-lab-reports/assets/146774867/b2525e98-4ba4-44ce-a513-06b514d3b3c8)
![Screen Shot 2023-11-05 at 4 42 23 PM](https://github.com/Naweidh/cse15l-lab-reports/assets/146774867/b94f3028-ab43-4cec-a38f-220e246deb5e)
![Screen Shot 2023-11-05 at 4 42 30 PM](https://github.com/Naweidh/cse15l-lab-reports/assets/146774867/5b872dd2-2080-4fac-b374-8f162166d076)


#The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown):
**Before: **
```
public class ArrayExamples {

  // Changes the input array to be in reversed order
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```
**After: **
```
public class ArrayExamples {
// Changes the input array to be in reversed order
static void reverseInPlace(int[] arr) {
  for(int i = 0; i < arr.length/2; i += 1) {
    int temp = arr[i];
    arr[i] = arr[arr.length - i - 1];
    arr[arr.length - i - 1] = temp;
  }
}

```
#Briefly describe why the fix addresses the issue:
The bug in the original code was that it swapped elements without considering the entire array. The fix addresses this issue by iterating only up to half of the array and swapping elements from both ends. Dividing the loop condition by 2 prevents unnecessary double-swapping.

##Part 2 - Researching Commands

#-r (recursive search): This option allows you to search for a pattern in all files within a directory and its subdirectories.
Example 1 - Searching for a specific text in all files within a directory and its subdirectories:
```
grep -r "array" ./Lab3
```
This command searches for "array" in all files within the specified directory and its subdirectories. It's useful for finding occurrences of a specific text across a project.

Example 2 - Searching for a pattern in all files and displaying line numbers:
```
grep -rn "array" ./Lab3
```
This command searches for "array" in all files within the specified directory and its subdirectories, displaying line numbers for each occurrence.

#-i (case-insensitive search): This option tells grep to perform a case-insensitive search.

Example 1 - Case-insensitive search for a specific word:

```grep -i "array" ArrayTests.java```
This command searches for "array" in file.txt regardless of the case.

Example 2 - Case-insensitive search in a directory and its subdirectories:

```grep -ri "array" ./Lab3```

This command searches for "array" case-insensitively in all files within the specified directory and its subdirectories.

#-l (show only filenames): This option tells grep to display only the filenames that contain the specified pattern, not the actual matching lines.

Example 1 - Finding files that contain a specific pattern:

```
grep -rl "array" ./Lab3
```

This command lists the filenames within the specified directory and its subdirectories that contain "array."

Example 2 - Finding files that contain a case-insensitive pattern:
```grep -ril "array" ./Lab3```

This command lists the filenames within the specified directory and its subdirectories that contain "array" case-insensitively.

#-v (invert the match): This option tells grep to display lines that do not contain the specified pattern.

Example 1 - Displaying lines that do not contain a word:

```grep -v "array" ArrayTests.java```

This command displays lines from file.txt that do not contain the word "array."

Example 2 - Inverting the match in a directory search:

```grep -rv "array" ./Lab3```
This command searches for lines that do not contain "array" in all files within the specified directory and its subdirectories.

Citations: 
“10 Examples of GREP Command in Unix and Linux.” Javarevisited, javarevisited.blogspot.com/2011/06/10-examples-of-grep-command-in-unix-and.html#axzz8JYXxxfEA. Accessed 19 Nov. 2023. 

