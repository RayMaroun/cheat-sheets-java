# Java Loops

Loops are used to repeat a block of code until a certain condition is met. In Java, there are three types of loops: for loop, while loop, and do-while loop.

## For Loop

The for loop is used when you know the number of times you want to repeat a block of code. Here's an example:

```java
for (int i = 1; i <= 5; i++) {
    System.out.println(i);
}
```

In this example, we're using a for loop to print the numbers 1 to 5. The loop starts with the initialization of a variable "i" with a value of 1. The loop continues until the condition "i <= 5" is true. After each iteration, the variable "i" is incremented by 1.

## While Loop

The while loop is used when you don't know the number of times you want to repeat a block of code, but you know the condition that must be met to continue the loop. Here's an example:

```java
int i = 1;
while (i <= 5) {
    System.out.println(i);
    i++;
}
```

In this example, we're using a while loop to print the numbers 1 to 5. The loop continues until the condition "i <= 5" is true. After each iteration, the variable "i" is incremented by 1.

## Do-While Loop

The do-while loop is similar to the while loop, but the block of code is executed at least once, even if the condition is false. Here's an example:

```java
int i = 1;
do {
    System.out.println(i);
    i++;
} while (i <= 5);
```

In this example, we're using a do-while loop to print the numbers 1 to 5. The loop continues until the condition "i <= 5" is true. After each iteration, the variable "i" is incremented by 1. The block of code is executed at least once, even if the condition is false.

## For-Each Loop

A for-each loop (also known as an enhanced for loop) is used to loop over an array or any other iterable object, such as a list or a set. Here's an example:

```java
int[] numbers = {1, 2, 3, 4, 5};
for (int number : numbers) {
    System.out.println(number);
}
```

In this example, we're using a for-each loop to print the elements of the "numbers" array.

## Break and Continue Statements

The break statement is used to exit a loop early, while the continue statement is used to skip to the next iteration of a loop. Here are some examples:

```java
for (int i = 1; i <= 10; i++) {
    if (i == 5) {
        break; // exit the loop when i is 5
    }
    System.out.println(i);
}

for (int i = 1; i <= 10; i++) {
    if (i % 2 == 0) {
        continue; // skip even numbers
    }
    System.out.println(i);
}
```

In the first example, we're using the break statement to exit the loop when the value of "i" is 5. In the second example, we're using the continue statement to skip even numbers.

## Creating a Menu Using a While Loop

You can create a simple menu using a while loop in Java. Here's an example:

```java
Scanner scanner = new Scanner(System.in);
boolean exit = false;
while (!exit) {
    System.out.println("1. Option 1");
    System.out.println("2. Option 2");
    System.out.println("3. Exit");
    System.out.print("Enter your choice: ");
    int choice = scanner.nextInt();
    switch (choice) {
        case 1:
            System.out.println("You chose Option 1");
            break;
        case 2:
            System.out.println("You chose Option 2");
            break;
        case 3:
            System.out.println("Goodbye!");
            exit = true;
            break;
        default:
            System.out.println("Invalid choice, try again");
            break;
    }
}
```

In this example, we're using a boolean variable "exit" to control the while loop. We initialize it to "false" at the beginning, and it will be set to "true" when the user chooses to exit the menu.

Inside the while loop, we print out the menu options and ask the user to enter their choice using the scanner object. We then use a switch statement to handle the different choices. If the user chooses Option 1 or Option 2, we print out a message indicating their choice. If the user chooses Exit, we print out a goodbye message and set the "exit" variable to true, which will cause the while loop to exit. Finally, if the user enters an invalid choice, we print out an error message and continue the loop.
