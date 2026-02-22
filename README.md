 Overview
This project demonstrates how to insert a new node at the **beginning of a singly linked list** in C.

In a singly linked list, each node contains:
- Data
- A pointer to the next node

When inserting at the beginning:
1. A new node is created.
2. The new node points to the current head.
3. The new node becomes the new head of the list.

---

 Source Code

```c
#include <stdio.h>
#include <stdlib.h>

// Define structure
struct Node {
    int data;
    struct Node* next;
};

// Function to insert at beginning
struct Node* insertAtBeginning(struct Node* head, int newData) {
    // Create new node
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));

    // Assign data
    newNode->data = newData;

    // Point new node to current head
    newNode->next = head;

    // Return new node as new head
    return newNode;
}

// Function to display linked list
void traverse(struct Node* head) {
    struct Node* temp = head;
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
}

int main() {
    struct Node* head = NULL;

    // Insert elements
    head = insertAtBeginning(head, 30);
    head = insertAtBeginning(head, 20);
    head = insertAtBeginning(head, 10);

    printf("Linked List after insertion at beginning:\n");
    traverse(head);

    return 0;
}
```

---

 Explanation

- `struct Node` → Defines the structure of a node.
- `insertAtBeginning()` → 
  - Allocates memory for a new node.
  - Assigns data to the new node.
  - Links new node to the current head.
  - Returns the new node as the updated head.
- `traverse()` → Displays all elements of the linked list.
- Insertion order:
  - Insert 30 → List: 30
  - Insert 20 → List: 20 → 30
  - Insert 10 → List: 10 → 20 → 30

---

 Sample Output

```
Linked List after insertion at beginning:
10 20 30
```

---

 Time Complexity
- Insertion at Beginning: **O(1)**
- Traversal: **O(n)**

---

Compile:
```
gcc insert_beginning.c -o insert
```

 Run:
```
./insert
```

---

 Concepts Used
- Structures in C
- Pointers
- Dynamic Memory Allocation (`malloc`)
- Linked List Insertion
- Linked List Traversal
