# **Queue in C++**
# Experiment 19  To study and implement Queue implementation using array. Menu options - i) Insert ii) Delete iii) Display iv) exit


A **queue** is a linear data structure that follows the **FIFO (First In, First Out)** principle, meaning the first element added is the first one to be removed. Below is a simple C program to implement a queue using an array, along with options for `Enqueue`, `Dequeue`, `Display`, and `Exit` using a `switch` statement.
### **Advantages of Queue**

1. **FIFO Principle**:
   - The **First In, First Out** nature of queues is ideal for managing tasks in the order they arrive (e.g., in operating systems and task scheduling).

2. **Efficient Task Scheduling**:
   - Queues are widely used in **task scheduling** systems like CPU scheduling and print spooling where tasks are completed in the order they were added.

3. **Handling Asynchronous Data**:
   - Queues are useful in **asynchronous** data transfer, such as buffering, where the order of data matters (e.g., I/O buffers, network data packets).

4. **Breadth-First Search (BFS)**:
   - Queues are crucial in **BFS** algorithms used in graph and tree traversal, where nodes are processed in the order they are discovered.

5. **Real-World Applications**:
   - Queues model many real-world scenarios like lines at a ticket counter or customer service, where the first person in line is the first to be served.

### **Disadvantages of Queue**

1. **Fixed Size (in Array-based Queues)**:
   - If implemented using arrays, the queue size is **fixed**, leading to **queue overflow** when it is full.

2. **No Random Access**:
   - Similar to stacks, queues do not support random access to elements. You can only access the element at the **front**, making it inefficient for some tasks.

3. **Wasted Memory (in Array-based Queues)**:
   - When elements are dequeued from the front in an array-based queue, the space cannot be reused, leading to **memory wastage** unless you reset or use a circular queue.

4. **Queue Overflow and Underflow**:
   - **Overflow** occurs when attempting to add an element to a full queue.
   - **Underflow** occurs when trying to remove an element from an empty queue.

5. **Circular Queue Implementation Needed**:
   - In some cases, to avoid memory wastage in array-based queues, you need to implement a **circular queue**, which can be more complex than a simple queue.
  
   The primary differences between **Queue** and **Stack** in C++ relate to their structure, behavior, and usage:

| Feature            | **Stack**                  | **Queue**                |
|--------------------|----------------------------|--------------------------|
| **Principle**       | LIFO (Last In, First Out)  | FIFO (First In, First Out)|
| **Operations**      | Push, Pop, Top             | Enqueue, Dequeue, Front   |
| **Insertion/Removal** | At the top                | Insertion at rear, removal at front |
| **Usage**           | Function call management, DFS, undo/redo | Task scheduling, BFS, real-time processing |
| **Access**          | Only top element           | Front for removal, rear for insertion |
| **Memory Usage**    | Less (one pointer)         | Slightly more (two pointers) |

In summary, **stack** is ideal for scenarios requiring LIFO behavior, while **queue** is used in situations requiring FIFO behavior.

## Code
~~~
#include <iostream>
using namespace std;

#define MAX 5

class Stack {
    int top;
    int stack[MAX];

public:
    Stack() {
        top = -1;  // Initialize top to -1 (empty stack)
    }

    // Push function to add an element to the stack
    void push(int value) {
        if (top == MAX - 1) {
            cout << "Stack Overflow! Cannot push more elements." << endl;
        } else {
            stack[++top] = value;
            cout << value << " pushed onto the stack." << endl;
        }
    }

    // Pop function to remove the top element from the stack
    void pop() {
        if (top == -1) {
            cout << "Stack Underflow! No elements to pop." << endl;
        } else {
            cout << stack[top--] << " popped from the stack." << endl;
        }
    }

    // Display function to print all elements in the stack
    void display() {
        if (top == -1) {
            cout << "Stack is empty." << endl;
        } else {
            cout << "Stack elements are: ";
            for (int i = top; i >= 0; i--) {
                cout << stack[i] << " ";
            }
            cout << endl;
        }
    }
};

int main() {
    Stack s;
    int choice, value;

    while (1) {
        // Display the menu options
        cout << "\nStack Operations Menu:\n";
        cout << "1. Push\n";
        cout << "2. Pop\n";
        cout << "3. Display\n";
        cout << "4. Exit\n";
        cout << "Enter your choice: ";
        cin >> choice;

        switch (choice) {
            case 1:  // Push
                cout << "Enter the value to push: ";
                cin >> value;
                s.push(value);
                break;

            case 2:  // Pop
                s.pop();
                break;

            case 3:  // Display
                s.display();
                break;

            case 4:  // Exit
                cout << "Exiting..." << endl;
                return 0;

            default:
                cout << "Invalid choice! Please enter a valid option." << endl;
        }
    }

    return 0;
}

~~~

## Code output 
![](https://github.com/Sundar13905/queue/blob/main/Exp_19_out.png)

## Conclusion
We leant how to implement queue in C++

