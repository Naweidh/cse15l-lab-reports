# Part 1- Debugging Scenario

## 1. Original Post: Description:
Hi everyone! I'm having a strange issue with my Java program. The output is not what I expected, and I'm not sure what's going wrong.

Calculator.java
```
public class Calculator {
    public static void main(String[] args) {
        int result = add(5, 7);
        System.out.println("Result: " + result);
    }

    public static int add(int a, int b) {
        return a - b; // Incorrect code causing the bug
    }
}

```
run.sh
```
javac Calculator.java
java Calculator

```
## 2. TA Response:
Can you try adding some debug statements or using a debugger to check the values of a and b inside the add method? It might give us more insight into what's going wrong.

## 3. Output of Bug:

![Screen Shot 2023-12-03 at 8 07 38 PM](https://github.com/Naweidh/cse15l-lab-reports/assets/146774867/846c7a42-8a45-439a-b658-ed202714f494)

## 4. Setup
The file & directory structure needed: 
-Calculator.java (Java file)
-run.sh (Bash script)

The contents of each file before fixing the bug:
-Calculator.java
```
public class Calculator {
    public static void main(String[] args) {
        int result = add(5, 7);
        System.out.println("Result: " + result);
    }

    public static int add(int a, int b) {
        return a - b; // Incorrect code causing the bug
    }
}

```
run.sh
```
javac Calculator.java
java Calculator

```

The full command line (or lines) you ran to trigger the bug:
- bash run.sh

A description of what to edit to fix the bug:
```
public static int add(int a, int b) {
    return a + b; // Fix the bug by changing subtraction to addition
}


```

# Part 2- Reflection
- From my lab experience, I didnt know much about a lot of the shorter commands to make working on code a lot easier and efficient rather than starting over or doing the long er way out. I learned a lot about how to problem solve with all the many situations that i was given as well. 

