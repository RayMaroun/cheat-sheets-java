## Detailed Java Stream Methods Cheat Sheet

### 1. `filter(Predicate<T>)`

#### Detailed Explanation

- **Purpose**: Filters elements based on a given condition.
- **Input**: `Predicate<T>` functional interface. This predicate is a lambda expression that takes an element of the stream and returns a boolean. If the predicate returns `true`, the element is included in the resulting stream.
- **Usage**: Commonly used to remove elements that don't meet certain criteria.

#### Example Breakdown

```java
List<String> matching = titles.stream()
     .filter(title -> title.toLowerCase().contains("halloween"))
     .collect(Collectors.toList());
```

- `titles.stream()`: Converts the list `titles` into a stream.
- `.filter(title -> ...)`: Applies the filter. The lambda expression checks if the title contains the word "halloween".
- `.collect(Collectors.toList())`: Collects the filtered stream back into a list.

### 2. `count()`

#### Detailed Explanation

- **Purpose**: Counts the number of elements in the stream after applying intermediate operations.
- **Return Type**: Returns a `long` value representing the count of elements.
- **Usage**: Useful for counting elements that match a certain condition.

#### Example Breakdown

```java
int count = titles.stream()
    .filter(title -> title.toLowerCase().contains("halloween"))
    .count();
```

- After the `filter` operation, `count` is used as a terminal operation to count the remaining elements.

### 3. `forEach(Consumer<? super T>)`

#### Detailed Explanation

- **Purpose**: Iterates over each element of the stream and performs a given action.
- **Input**: `Consumer<T>` functional interface. It accepts an element and returns no result. The lambda expression defines the action to be performed on each element.
- **Usage**: Commonly used for executing side-effect operations (like printing out elements).

#### Example Breakdown

```java
titles.stream()
    .filter(title -> title.toLowerCase().contains("halloween"))
    .forEach(System.out::println);
```

- `System.out::println`: Method reference that acts as a `Consumer`, printing each element.

### 4. `sorted()`

#### Detailed Explanation

- **Purpose**: Sorts the elements of the stream.
- **Behavior**: By default, it sorts the stream in natural order. If a `Comparator` is provided, it uses that for sorting.
- **Usage**: Useful for ordering elements in a specific manner.

#### Example Breakdown

```java
titles.stream()
   .filter(title -> title.toLowerCase().contains("halloween"))
   .sorted()
   .forEach(System.out::println);
```

- `.sorted()`: Sorts the stream. In this case, the natural ordering of strings (alphabetical) is used.

### 5. `map(Function<? super T, ? extends R>)`

#### Detailed Explanation

- **Purpose**: Transforms each element of the stream into another form.
- **Input**: `Function<T, R>` functional interface. It takes an element and returns another object, potentially of a different type.
- **Usage**: Used for converting or mapping each element to a new form.

#### Example Breakdown

```java
List<Integer> squaresList = numbers.stream()
             .map(num -> num * num)
             .distinct()
             .collect(Collectors.toList());
```

- `.map(num -> num * num)`: Applies the function to each element (squaring the number in this case).

### 6. `reduce(BinaryOperator<T>)`

#### Detailed Explanation

- **Purpose**: Reduces the elements of the stream to a single value.
- **Input**: Takes an initial value and a `BinaryOperator<T>` (a lambda expression). The lambda takes two parameters: a running total and the current element.
- **Usage**: Common for aggregating elements, like summing numbers or concatenating strings.

#### Example Breakdown

```java
int sum = numbers.stream()
             .reduce(0, (temp, num) -> temp + num);
```

- `0`: The initial value for the aggregation.
- `(temp, num) -> temp + num`: Defines how to aggregate elements. In this case, it's summing up the numbers.

---

### Additional Concepts

- **Stream Creation**: Streams are created from collections or arrays using `.stream()`.
- **Intermediate vs Terminal Operations**: Intermediate operations (like `filter` and `map`) return a new stream. They are lazy and do not execute until a terminal operation (like `forEach` or `count`) is invoked.
- **Lambda Expressions**: These are short blocks of code that are passed around, commonly used in stream operations for defining conditions, functions, and operations.
