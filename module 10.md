EXP NO:16 C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST.
Aim:
To write a C program to search a given element in the given linked list.

Algorithm:
1.	Define the structure for a node in a linked list.
2.	Define the search function to find a specific character in the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the search function and perform other linked list operations as needed.
 
Program:

    #include <stdio.h>
    #include <stdlib.h>
    
    struct Node {
        int data;
        struct Node* next;
    };
    
    void insert(struct Node** head, int data) {
        struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
        newNode->data = data;
        newNode->next = *head;
        *head = newNode;
    }
    
    int search(struct Node* head, int key) {
        struct Node* temp = head;
        while (temp != NULL) {
            if (temp->data == key) {
                return 1;  // Element found
            }
            temp = temp->next;
        }
        return 0;  // Element not found
    }
    
    void display(struct Node* head) {
        struct Node* temp = head;
        while (temp != NULL) {
            printf("%d -> ", temp->data);
            temp = temp->next;
        }
        printf("NULL\n");
    }
    
    int main() {
        struct Node* head = NULL;
        int key, found;

    insert(&head, 10);
    insert(&head, 20);
    insert(&head, 30);
    insert(&head, 40);
    insert(&head, 50);

    printf("Linked List: ");
    display(head);

    printf("Enter the element to search: ");
    scanf("%d", &key);

    found = search(head, key);
    if (found) {
        printf("Element %d found in the linked list.\n", key);
    } else {
        printf("Element %d not found in the linked list.\n", key);
    }

    return 0;
}

Output:

    Linked List: 50 -> 40 -> 30 -> 20 -> 10 -> NULL
    Enter the element to search: 30
    Element 30 found in the linked list.




Result:
Thus, the program to search a given element in the given linked list is verified successfully.


 
EXP NO:17  PROGRAM TO INSERT A NODE IN A LINKED LIST.
Aim:
To write a C program to insert a node in a linked list.
Algorithm:
1.	Define the structure for a node in a linked list
2.	Define the insert function to insert a new node with character data at the end of the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the insert function and perform other linked list operations as needed.
 
Program:

    #include <stdio.h>
    #include <stdlib.h>
    
    struct Node {
        int data;
        struct Node* next;
    };
    
    void insertAtBeginning(struct Node** head, int data) {
        struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
        newNode->data = data;
        newNode->next = *head;
        *head = newNode;
    }
    
    void insertAtEnd(struct Node** head, int data) {
        struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
        struct Node* temp = *head;
        newNode->data = data;
        newNode->next = NULL;
        
        if (*head == NULL) {
            *head = newNode;
            return;
        }
        
        while (temp->next != NULL) {
            temp = temp->next;
        }
        temp->next = newNode;
    }
    
    void insertAtPosition(struct Node** head, int data, int position) {
        struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
        struct Node* temp = *head;
        newNode->data = data;
    
        if (position == 0) {
            newNode->next = *head;
            *head = newNode;
            return;
        }
    
        for (int i = 0; temp != NULL && i < position - 1; i++) {
            temp = temp->next;
        }
    
        if (temp == NULL) {
            printf("Position is out of range\n");
            return;
        }
    
        newNode->next = temp->next;
        temp->next = newNode;
    }
    
    void display(struct Node* head) {
        struct Node* temp = head;
        while (temp != NULL) {
            printf("%d -> ", temp->data);
            temp = temp->next;
        }
        printf("NULL\n");
    }
    
    int main() {
        struct Node* head = NULL;
        
        insertAtBeginning(&head, 10);
        insertAtEnd(&head, 20);
        insertAtEnd(&head, 30);
        insertAtBeginning(&head, 5);
        insertAtPosition(&head, 15, 2);
    
        printf("Linked List: ");
        display(head);
    
        return 0;
    }


Output:

     Linked List: 5 -> 10 -> 15 -> 20 -> 30 -> NULL


 
Result:
Thus, the program to insert a node in a linked list is verified successfully.


 
EXP NO:18 C PROGRAM TO TRAVERSE A DOUBLY LINKED LIST
Aim:
To write a C program to traverse a doubly linked list.

Algorithm:
1.	Initialize a temporary pointer (temp) to the head of the list.
2.	Use a while loop to traverse the list until the end (temp == NULL) is reached.
3.	Inside the loop, print the data of the current node.
4.	Move to the next node by updating the temp pointer to point to the next node (temp = temp->next).
 
Program:

    #include <stdio.h>
    #include <stdlib.h>
    
    struct Node {
        int data;
        struct Node* next;
        struct Node* prev;
    };
    
    void insertAtEnd(struct Node** head, int data) {
        struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
        struct Node* temp = *head;
        newNode->data = data;
        newNode->next = NULL;
        newNode->prev = NULL;
    
        if (*head == NULL) {
            *head = newNode;
            return;
        }
    
        while (temp->next != NULL) {
            temp = temp->next;
        }
    
        temp->next = newNode;
        newNode->prev = temp;
    }
    
    void traverseForward(struct Node* head) {
        struct Node* temp = head;
        printf("Forward traversal: ");
        while (temp != NULL) {
            printf("%d -> ", temp->data);
            temp = temp->next;
        }
        printf("NULL\n");
    }
    
    void traverseBackward(struct Node* head) {
        struct Node* temp = head;
        if (temp == NULL) {
            return;
        }
    
        while (temp->next != NULL) {
            temp = temp->next;
        }
    
        printf("Backward traversal: ");
        while (temp != NULL) {
            printf("%d -> ", temp->data);
            temp = temp->prev;
        }
        printf("NULL\n");
    }
    
    int main() {
        struct Node* head = NULL;
    
        insertAtEnd(&head, 10);
        insertAtEnd(&head, 20);
        insertAtEnd(&head, 30);
        insertAtEnd(&head, 40);
        insertAtEnd(&head, 50);
    
        traverseForward(head);
        traverseBackward(head);
    
        return 0;
    }


Output:

    Forward traversal: 10 -> 20 -> 30 -> 40 -> 50 -> NULL
    Backward traversal: 50 -> 40 -> 30 -> 20 -> 10 -> NULL


Result:
Thus, the program to traverse a doubly linked list is verified successfully. 



EXP NO:19 C PROGRAM TO INSERT AN ELEMENT IN DOUBLY LINKED LIST
Aim:
To write a C program to insert an element in doubly linked list

Algorithm:
1.	Create a new node (newNode) and allocate memory for it.
2.	Set the data of the new node to the provided value.
3.	If the list is empty, set the new node as the head.
4.	If the list is not empty, traverse the list to find the last node.
5.	Set the new node's prev pointer to the last node and update the last node's next pointer to the new node.
 
Program:

     #include <stdio.h>
     #include <stdlib.h>
     
     struct Node {
         int data;
         struct Node* next;
         struct Node* prev;
     };
     
     void insertAtBeginning(struct Node** head, int data) {
         struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
         newNode->data = data;
         newNode->next = *head;
         newNode->prev = NULL;
     
         if (*head != NULL) {
             (*head)->prev = newNode;
         }
         *head = newNode;
     }
     
     void insertAtEnd(struct Node** head, int data) {
         struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
         struct Node* temp = *head;
         newNode->data = data;
         newNode->next = NULL;
     
         if (*head == NULL) {
             newNode->prev = NULL;
             *head = newNode;
             return;
         }
     
         while (temp->next != NULL) {
             temp = temp->next;
         }
         temp->next = newNode;
         newNode->prev = temp;
     }
     
     void insertAtPosition(struct Node** head, int data, int position) {
         struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
         struct Node* temp = *head;
         newNode->data = data;
     
         if (position == 0) {
             insertAtBeginning(head, data);
             return;
         }
     
         for (int i = 0; temp != NULL && i < position - 1; i++) {
             temp = temp->next;
         }
     
         if (temp == NULL) {
             printf("Position is out of range\n");
             return;
         }
     
         newNode->next = temp->next;
         if (temp->next != NULL) {
             temp->next->prev = newNode;
         }
         temp->next = newNode;
         newNode->prev = temp;
     }
     
     void display(struct Node* head) {
         struct Node* temp = head;
         while (temp != NULL) {
             printf("%d <-> ", temp->data);
             temp = temp->next;
         }
         printf("NULL\n");
     }
     
     int main() {
         struct Node* head = NULL;
     
         insertAtBeginning(&head, 10);
         insertAtEnd(&head, 20);
         insertAtEnd(&head, 30);
         insertAtBeginning(&head, 5);
         insertAtPosition(&head, 15, 2);
     
         printf("Doubly Linked List: ");
         display(head);
     
         return 0;
     }


Output:

    Doubly Linked List: 5 <-> 10 <-> 15 <-> 20 <-> 30 <-> NULL
    


Result:
Thus, the program to insert an element in doubly linked list is verified successfully.




EXP NO:20 C FUNCTION TO DELETE A GIVEN ELEMENT IN THE GIVEN LINKED LIST




Aim:
To write a C function that deletes a given element from a linked list.

Algorithm:
1.	Check if the Linked List is Empty:
o	If the head of the linked list is NULL, print a message indicating the list is empty and exit the function.
2.	Traverse the Linked List:
o	Start from the head node and iterate through the list to find the node that contains the given element (data).
3.	Handle Deletion of the First Node:
o	If the element to be deleted is found in the head node:
	Update the head of the linked list to point to the next node (i.e., head = head->next).
	Free the memory allocated to the node to be deleted.
	Exit the function.
4.	Traverse and Delete from the Middle or End:
o	If the element is not in the head node, continue traversing the list by checking each node’s next pointer.
o	When the node with the element is found, update the previous node’s next pointer to point to the next node of the node to be deleted (prev->next = current->next).
o	Free the memory allocated to the node to be deleted.
5.	Handle the Case when the Element is Not Found:
o	If the element is not found in any node, print a message indicating the element is not present in the list.
6.	End the Function.


Program:

     #include <stdio.h>
     #include <stdlib.h>
     
     struct Node {
         int data;
         struct Node* next;
     };
     
     void insertAtEnd(struct Node** head, int data) {
         struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
         struct Node* temp = *head;
         newNode->data = data;
         newNode->next = NULL;
         
         if (*head == NULL) {
             *head = newNode;
             return;
         }
         
         while (temp->next != NULL) {
             temp = temp->next;
         }
         temp->next = newNode;
     }
     
     void deleteElement(struct Node** head, int key) {
         struct Node* temp = *head;
         struct Node* prev = NULL;
         
         if (temp != NULL && temp->data == key) {
             *head = temp->next;
             free(temp);
             printf("Element %d deleted from the linked list\n", key);
             return;
         }
     
         while (temp != NULL && temp->data != key) {
             prev = temp;
             temp = temp->next;
         }
         
         if (temp == NULL) {
             printf("Element %d not found in the linked list\n", key);
             return;
         }
     
         prev->next = temp->next;
         free(temp);
         printf("Element %d deleted from the linked list\n", key);
     }
     
     void display(struct Node* head) {
         struct Node* temp = head;
         while (temp != NULL) {
             printf("%d -> ", temp->data);
             temp = temp->next;
         }
         printf("NULL\n");
     }
     
     int main() {
         struct Node* head = NULL;
     
         insertAtEnd(&head, 10);
         insertAtEnd(&head, 20);
         insertAtEnd(&head, 30);
         insertAtEnd(&head, 40);
         insertAtEnd(&head, 50);
     
         printf("Linked List before deletion: ");
         display(head);
     
         deleteElement(&head, 30);
         deleteElement(&head, 10);
         deleteElement(&head, 100);
     
         printf("Linked List after deletion: ");
         display(head);
     
         return 0;
     }


Output:

    Linked List before deletion: 10 -> 20 -> 30 -> 40 -> 50 -> NULL
      Element 30 deleted from the linked list
      Element 10 deleted from the linked list
      Element 100 not found in the linked list
      Linked List after deletion: 20 -> 40 -> 50 -> NULL





Result:
Thus, the function that deletes a given element from a linked list is verified successfully.





