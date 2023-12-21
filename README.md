# ✨ Challenges-in-Dart

## ✨ Stacks:
## Challenges:

**Challenge 1: Reverse a List ->** Create a function that prints the contents of a list in reverse order.
- **My Solution**

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

**Challenge 2: Balance the Parentheses ->** Check for balanced parentheses. Given a string, check if there are ( and ) characters, and return true if the parentheses in the string are balanced.
- **My Solution**

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

## ✨ LinkedList:
## Challenges:

**Challenge 1: Print in Reverse ->** Create a function that prints the nodes of a linked list in reverse order
- **My Solution**

```dart
class Node {
  final int data;
  Node? next;

  Node(this.data);
}

void InReverse(Node? head) {
  if (head == null) return;

  InReverse(head.next);

  print(head.data);
}

void main() {
  Node head = Node(1);
  head.next = Node(2);
  head.next!.next = Node(3);

  InReverse(head); 
}
```

**Challenge 2: Find the Middle Node ->** Create a function that finds the middle node of a linked list.
- **My Solution**

```dart
class Node {
 int value;
 Node? next;
 Node(this.value, [this.next]);
}

Node? findMiddleNode(Node? head) {
 if (head == null) {
   return null;
 }

 Node? slow = head;
 Node? fast = head;

 while (fast != null && fast.next != null) {
   slow = slow!.next;
   fast = fast.next!.next;
 }

 return slow;
}

void main() {
  Node node1 = Node(1);
  Node node2 = Node(2);
  Node node3 = Node(3);
  Node node4 = Node(4);

  node1.next = node2;
  node2.next = node3;
  node3.next = node4;

  Node? middleNode1 = findMiddleNode(node1);
  print('Middle is: ${middleNode1?.value}');
}
```

**Challenge 3: Reverse a Linked List ->** Create a function that reverses a linked list. You do this by manipulating the nodes so that they’re linked in the other direction.
- **My Solution**

```dart
class Node {
  final int data;
  Node? next;
  Node(this.data, [this.next]);
}

Node? reverseList(Node? head) {
  if (head == null || head.next == null) return head;

  Node? prev = null;
  Node? current = head;

  while (current != null) {
    var nextNode = current.next;
    current.next = prev;
    prev = current;
    current = nextNode;
  }

  return prev;
}

void main() {
  var head = Node(1);
  head.next = Node(2);
  head.next!.next = Node(3);

  var reversedHead = reverseList(head);

  var curr = reversedHead;
  while (curr != null) {
    print(curr.data);
    curr = curr.next;
  }
}  
```

**Challenge 4: Remove All Occurrences ->** Create a function that removes all occurrences of a specific element from a linked list. The implementation is similar to the removeAfter method that you implemented earlier
- **My Solution**

```dart
class Node {
  int value;
  Node? next;

  Node(this.value) : next = null;

  void addNode(int value) {
    if (next == null) {
      next = Node(value);
    } else {
      next!.addNode(value);
    }
  }
}

Node? removeAllOccurrences(Node? head, int targetValue) {
  while (head != null && head.value == targetValue) {
    head = head.next;
  }

  Node? current = head;
  Node? prev = null;

  while (current != null) {
    if (current.value == targetValue) {
      prev!.next = current.next;
    } else {
      prev = current;
    }

    current = current.next;
  }

  return head;
}

void printLinkedList(Node? head) {
  while (head != null) {
    print(head.value);
    head = head.next;
  }
}

void main() {
  var originalList = Node(1);
  originalList.addNode(3);
  originalList.addNode(3);
  originalList.addNode(3);
  originalList.addNode(4);

  print('Before removing occurrences:');
  printLinkedList(originalList);

  int targetValue = 3;
  Node? modifiedList = removeAllOccurrences(originalList, targetValue);

  print('\nAfter removing occurrences of $targetValue:');
  printLinkedList(modifiedList);
}
```
