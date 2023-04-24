# Java Strings

## Creating Strings

In Java, you can create a string using the following syntax:

```java
String myString = "Hello, world!";
```

This creates a string literal with the value "Hello, world!" and assigns it to the variable myString.

## Escaping Quotes

To include quotes within a string literal, you can use the backslash () character to escape the quote:

```java
String myString = "She said, \"Hello, world!\"";
```

This will create a string with the value "She said, "Hello, world!"".

## Comparing Strings

To compare two strings for equality in Java, you can use the equals() method:

```java
String str1 = "hello";
String str2 = "world";
if (str1.equals(str2)) {
System.out.println("The strings are equal");
} else {
System.out.println("The strings are not equal");
}
```

## String Methods

### trim()

The trim() method removes whitespace from the beginning and end of a string:

```java
String myString = " Hello, world! ";
String trimmedString = myString.trim();
```

After executing this code, trimmedString will contain the value "Hello, world!".

### length()

The length() method returns the length of a string:

```java
String myString = "Hello, world!";
int length = myString.length();
```

After executing this code, length will contain the value 13.

### toUpperCase() and toLowerCase()

The toUpperCase() method converts a string to uppercase, while the toLowerCase() method converts a string to lowercase:

```java
String myString = "Hello, world!";
String upperCaseString = myString.toUpperCase();
String lowerCaseString = myString.toLowerCase();
```

After executing this code, upperCaseString will contain the value "HELLO, WORLD!", while lowerCaseString will contain the value "hello, world!".

### startsWith() and endsWith()

The startsWith() method checks if a string starts with a specified prefix, while the endsWith() method checks if a string ends with a specified suffix:

```java
String myString = "Hello, world!";
boolean startsWithHello = myString.startsWith("Hello");
boolean endsWithWorld = myString.endsWith("world!");
```

After executing this code, startsWithHello will be true, while endsWithWorld will be true.

### charAt()

The charAt() method returns the character at a specified index in a string:

```java
String myString = "Hello, world!";
char firstChar = myString.charAt(0);
```

After executing this code, firstChar will contain the value 'H'.

### indexOf()

The indexOf() method returns the index of the first occurrence of a specified character or substring within a string:

```java
String myString = "Hello, world!";
int index = myString.indexOf("world");
```

After executing this code, index will contain the value 7.

### substring()

The substring() method returns a substring of a string, starting at a specified index:

```java
String myString = "Hello, world!";
String subString = myString.substring(7);
```

After executing this code, subString will contain the value "world!".

### split()

The split() method is used to split a string into an array of substrings based on a specified delimiter:

```java
String myString = "apple,banana,orange";
String[] fruits = myString.split(",");
```

After executing this code, fruits will be an array with three elements: {"apple", "banana", "orange"}.

## Converting String to Number

To convert a string to a numeric value, you can use the following methods:

Integer.parseInt() for converting to an int
Double.parseDouble() for converting to a double
Float.parseFloat() for converting to a float
Long.parseLong() for converting to a long
Here is an example of converting a string to an integer:

```java
String myString = "123";
int myInt = Integer.parseInt(myString);
```

After executing this code, myInt will contain the value 123.

## Converting String to Date

To convert a string to a date object, you can use the SimpleDateFormat class. Here is an example of converting a string to a date:

```java
String dateString = "2022-04-24";
SimpleDateFormat dateFormat = new SimpleDateFormat("yyyy-MM-dd");
Date date = dateFormat.parse(dateString);
```

After executing this code, date will contain a Date object representing April 24, 2022.

## StringBuilder

The StringBuilder class is used to create and manipulate mutable strings. It provides methods for appending, inserting, and deleting characters in a string. Here is an example of using StringBuilder:

```java
StringBuilder sb = new StringBuilder();
sb.append("Hello");
sb.append(", ");
sb.append("world!");
sb.insert(5, "beautiful ");
sb.delete(12, 14);
String finalString = sb.toString();
```

After executing this code, finalString will contain the value "Hello, beautiful world".
