# Challenges-in-Dart

## Stacks:
## Challenges:

**Challenge 1: Reverse a List** -> Create a function that prints the contents of a list in reverse order.
- **my solution**

```dart
void main() {
  List<int> numbers = [1, 2, 3, 4, 5];
  List<int> stack = [];

  for (int i = numbers.length - 1; i >= 0; i--) {
    stack.add(numbers[i]);
  }

  print(stack); 
}
```

**Challenge 2: Balance the Parentheses** -> Check for balanced parentheses. Given a string, check if there are ( and ) characters, and return true if the parentheses in the string are balanced.
- **my solution**

```dart
bool isBalanced(String input) {
  int counter = 0;

  for (int i = 0; i < input.length; i++) {
    String char = input[i];

    if (char == '(') {
      counter++;
    } else if (char == ')') {
      counter--;

    }
  }
  return counter == 0;
}

void main() {
  String str1 = "h((e))llo(world)()";
  print(isBalanced(str1));  

  String str2 = "(hello world";
  print(isBalanced(str2));  
}
```

