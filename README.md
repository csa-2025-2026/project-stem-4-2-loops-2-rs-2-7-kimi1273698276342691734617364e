# unit-4-2-assignment

## Git Config
```
git config user.name "user"
git config user.email "email"
```

## Compiling and Running Java Programs
Note that since the shape classes are separate classes, you will need to compile ALL the files (at least one time).  You can do this by running
```
javac *.java
```
The star means to compile every file that is a Java file type.

Run your code by running
```
java Main.java
```

After you compile the shape classes, you only need to compile and run `Main.java` as usual.

# Instructions  

## Problem 1
Ask the user for two numbers. Print only the odd numbers between them. You should also print the two numbers if they are odd.  You may assume that the first number entered is less than the second number entered.

Sample Run 1:
```
Enter two numbers:
2
11

3 5 7 9 11
```
Sample Run 2:
```
Enter two numbers:
10
44

11 13 15 17 19 21 23 25 27 29 31 33 35 37 39 41 43
```

## Problem 2
Write a program which takes a positive `int` input from the user, then prints the digits of that number in reverse order.

**Sample Run:**
```
Enter a positive integer:
> 2587
7
8
5
2
```

## Problem 3
Write a program which takes a positive int input from the user, then prints the digits of that number in their places. You should separate the digits using spaces of line breaks so they appear individually.

Sample run:
```
Enter a positive integer:
> 2587
7
80
500
2000
```

## Sample Solutions
```java
Scanner sc = new Scanner(System.in);

// Problem 1
int a;
int b;

System.out.println("Enter two numbers:");
a = sc.nextInt();
b = sc.nextInt();

while (a <= b)
{
  if (a % 2 == 1)
  {
    System.out.print(a + " ");
  }
  a++;
}

// Problem 2
System.out.print("Enter a positive integer:\n> ");
int num = sc.nextInt();
while (num > 0)
{
  int last_digit = num % 10;
  System.out.println(last_digit);

  num /= 10;
}

// Problem 3
int N;
int degree = 0;

System.out.print("Enter a positive integer:\n> ");
N = sc.nextInt();

while (N > 0)
{
  // These two lines are the
  // "print every digit" algorithm
  int last_digit = N % 10;
  N /= 10;

  // note that pow always returns a double, so it needs
  // to be stored in a double
  double place_value = Math.pow(10, degree);
  System.out.println(last_digit * place_value);
  
  degree++;  // 1's place → 10's place; 10's place → 100's place, and so on
}

sc.close();
```
