# Java Arrays

In Java, an array is a collection of similar data types that is stored in a contiguous block of memory. The size of an array is fixed at the time of declaration and cannot be changed during runtime.

## Declaring an array:

To declare an array in Java, you need to specify the data type of the elements and the size of the array. Here's an example:

```java
int[] numbers = new int[5];
```

In this example, we're declaring an array of integers named "numbers" with a size of 5. The "new" keyword is used to create the array object in memory.

## Accessing array elements:

You can access the elements of an array using the index, which starts from 0. Here's an example:

```java
int[] numbers = {10, 20, 30, 40, 50};

// accessing the first element
int first = numbers[0];

// accessing the last element
int last = numbers[numbers.length - 1];
```

In this example, we're declaring an array of integers named "numbers" and initializing it with some values. We're accessing the first element by using the index 0 and the last element by using the index "numbers.length - 1".

## Sorting an Array

You can sort an array in Java using the Arrays.sort() method. Here's an example:

```java
int[] numbers = {5, 2, 8, 1, 9};
Arrays.sort(numbers);
for (int number : numbers) {
    System.out.println(number);
}
```

In this example, we're using the `Arrays.sort()` method to sort the "numbers" array in ascending order.

## Copying an Array

You can copy an array in Java using the `System.arraycopy()` method. Here's an example:

```java
int[] arr1 = {1, 2, 3, 4, 5};
int[] arr2 = new int[arr1.length];
System.arraycopy(arr1, 0, arr2, 0, arr1.length);
```

In this example, we're copying the elements of `arr1` to `arr2` using `System.arraycopy()`. The first argument to the method is the source array (in this case, `arr1`). The second argument is the starting index in the source array (in this case, 0). The third argument is the destination array (in this case, `arr2`). The fourth argument is the starting index in the destination array (in this case, 0). Finally, the fifth argument is the number of elements to copy (in this case, the length of `arr1`).

## Adding an Element to an Array

In Java, you cannot add an element to an array once it has been created. However, you can create a new array with a larger size and copy the elements of the old array to the new array, along with the new element. Here's an example:

```java
int[] numbers = {1, 2, 3};
int newElement = 4;
int[] newNumbers = new int[numbers.length + 1];
for (int i = 0; i < numbers.length; i++) {
    newNumbers[i] = numbers[i];
}
newNumbers[numbers.length] = newElement;
```

In this example, we're creating a new array "newNumbers" with a larger size and copying the elements of the "numbers" array to the new array. We're also adding a new element "newElement" to the end of the new array.
