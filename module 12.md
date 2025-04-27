

EXP NO 26: C PROGRAM TO DISPLAY STACK ELEMENTS USING LINKED LIST.
Aim:
To write a C program to display stack elements using linked list.

Algorithm:
1.	Define a structure Node with two members: data to store the integer value and next to point to the next node in the linked list.
2.	Declare a global variable head representing the starting node of the linked list.
3.	Define a function display to print the elements of the linked list.
4.	Declare a pointer p and initialize it with the head of the linked list.
5.	Use a while loop to traverse the linked list:
6.	Print the data of the current node.
7.	Move to the next node using the next pointer.
 
Program:

     #include <stdio.h>
     #include <stdlib.h>
     
     struct Node {
         int data;
         struct Node* next;
     };
     
     struct Node* top = NULL;
     
     void push(int value) {
         struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
         newNode->data = value;
         newNode->next = top;
         top = newNode;
     }
     
     void display() {
         struct Node* temp = top;
         if (top == NULL) {
             printf("Stack is empty\n");
             return;
         }
         printf("Stack elements:\n");
         while (temp != NULL) {
             printf("%d\n", temp->data);
             temp = temp->next;
         }
     }
     
     int main() {
         push(10);
         push(20);
         push(30);
     
         display();
     
         return 0;
     }


Output:

    Stack elements:
    30
    20
    10



Result:
Thus, the program to display stack elements using linked list is verified successfully. 



EXP.NO 27: C PROGRAM TO POP AN ELEMENT FROM THE GIVEN STACK USING 
LINKED LIST.
Aim:
To write a C program to pop an element from the given stack using liked list.

Algorithm:
1.	Check for Empty Stack
2.	If head is equal to NULL, Print "Stack is empty."
3.	Else Proceed to the next step.
4.	Set head to point to the next node in the stack.
 
Program:

    #include <stdio.h>
    #include <stdlib.h>
    
    struct Node {
        int data;
        struct Node* next;
    };
    
    struct Node* top = NULL;
    
    void push(int value) {
        struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
        newNode->data = value;
        newNode->next = top;
        top = newNode;
    }
    
    void pop() {
        if (top == NULL) {
            printf("Stack Underflow. Cannot pop.\n");
            return;
        }
        struct Node* temp = top;
        printf("Popped element: %d\n", top->data);
        top = top->next;
        free(temp);
    }
    
    void display() {
        struct Node* temp = top;
        if (top == NULL) {
            printf("Stack is empty\n");
            return;
        }
        printf("Stack elements:\n");
        while (temp != NULL) {
            printf("%d\n", temp->data);
            temp = temp->next;
        }
    }
    
    int main() {
        push(10);
        push(20);
        push(30);
    
        display();
    
        pop();
        pop();
    
        display();
    
        return 0;
    }


Output:

    Stack elements:
    30
    20
    10
    Popped element: 30
    Popped element: 20
    Stack elements:
    10




Result:
Thus, the program to pop an element from the given stack using liked list is verified successfully.

 
EXP NO:28 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING LINKED LIST.
Aim:
To write a C program to display queue elements using linked list.
Algorithm:
1.	Check if Queue is Empty
2.	Display Queue Elements
3.	Print the data of the current node pointed to by front
4.	Update front to point to the next node.
5.	End the display function.
 
Program:

     #include <stdio.h>
     #include <stdlib.h>
     
     struct Node {
         int data;
         struct Node* next;
     };
     
     struct Node* front = NULL;
     struct Node* rear = NULL;
     
     void enqueue(int value) {
         struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
         newNode->data = value;
         newNode->next = NULL;
     
         if (rear == NULL) {
             front = rear = newNode;
         } else {
             rear->next = newNode;
             rear = newNode;
         }
     }
     
     void display() {
         struct Node* temp = front;
         if (front == NULL) {
             printf("Queue is empty\n");
             return;
         }
     
         printf("Queue elements:\n");
         while (temp != NULL) {
             printf("%d ", temp->data);
             temp = temp->next;
         }
         printf("\n");
     }
     
     int main() {
         enqueue(10);
         enqueue(20);
         enqueue(30);
         enqueue(40);
     
         display();
     
         return 0;
     }

Output:

    Queue elements:
    10 20 30 40


Result:
Thus, the program to display queue elements using linked list is verified successfully.


 
EXP NO:29 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING LINKED LIST

Aim:
To write a C program to insert elements in queue using linked list

Algorithm:
1.	Allocate Memory for New Node
2.	Set Data and Next Pointer
3.	Check if Queue is Empty
4.	Set both front and rear to point to the new node p.
5.	Set the next pointer of the current rear to point to the new node p.
6.	End of Enqueue Operation
 
Program:

    #include <stdio.h>
    #include <stdlib.h>
    
    struct Node {
        int data;
        struct Node* next;
    };
    
    struct Node* front = NULL;
    struct Node* rear = NULL;
    
    void enqueue(int value) {
        struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
        newNode->data = value;
        newNode->next = NULL;
    
        if (rear == NULL) {
            front = rear = newNode;
        } else {
            rear->next = newNode;
            rear = newNode;
        }
        printf("%d added to the queue\n", value);
    }
    
    void display() {
        struct Node* temp = front;
        if (front == NULL) {
            printf("Queue is empty\n");
            return;
        }
    
        printf("Queue elements:\n");
        while (temp != NULL) {
            printf("%d ", temp->data);
            temp = temp->next;
        }
        printf("\n");
    }
    
    int main() {
        enqueue(10);
        enqueue(20);
        enqueue(30);
        enqueue(40);
    
        display();
    
        return 0;
    }


Output:

    10 added to the queue
    20 added to the queue
    30 added to the queue
    40 added to the queue
    Queue elements:
    10 20 30 40


Result:
Thus, the program to insert elements in queue using linked list is verified successfully.



EXP NO:30 C FUNCTION TO FIND THE PEEK OF QUEUE USING LINKED LIST.


Aim:

The aim of this function is to retrieve the "peek" (the front element) of a queue implemented using a linked list

Algorithm:

1.	Check if the queue is empty:
o	If the queue is empty (i.e., the front pointer is NULL), return an error or a message indicating that the queue is empty.
2.	Access the front element:
o	If the queue is not empty, return the data stored in the front node of the linked list (i.e., the element at the head of the queue).

Program:

    #include <stdio.h>
    #include <stdlib.h>
    
    struct Node {
        int data;
        struct Node* next;
    };
    
    struct Node* front = NULL;
    struct Node* rear = NULL;
    
    void enqueue(int value) {
        struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
        newNode->data = value;
        newNode->next = NULL;
    
        if (rear == NULL) {
            front = rear = newNode;
        } else {
            rear->next = newNode;
            rear = newNode;
        }
        printf("%d added to the queue\n", value);
    }
    
    void display() {
        struct Node* temp = front;
        if (front == NULL) {
            printf("Queue is empty\n");
            return;
        }
    
        printf("Queue elements:\n");
        while (temp != NULL) {
            printf("%d ", temp->data);
            temp = temp->next;
        }
        printf("\n");
    }
    
    int peek() {
        if (front == NULL) {
            printf("Queue is empty\n");
            return -1;  // Indicating queue is empty
        }
        return front->data;
    }
    
    int main() {
        enqueue(10);
        enqueue(20);
        enqueue(30);
        enqueue(40);
    
        display();
    
        printf("Peek of the queue: %d\n", peek());
    
        return 0;
    }


Output:

    10 added to the queue
    20 added to the queue
    30 added to the queue
    40 added to the queue
    Queue elements:
    10 20 30 40 
    Peek of the queue: 10



Result:

Thus, the program to retrieve the "peek" (the front element) of a queue implemented using a linked list is verified successfully.


