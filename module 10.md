EXP NO:16 C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST.
Aim:
To write a C program to search a given element in the given linked list.

Algorithm:
1.	Define the structure for a node in a linked list.
2.	Define the search function to find a specific character in the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the search function and perform other linked list operations as needed.
 
Program:
```
#include <stdio.h>
#include<stdlib.h>
struct Node
{
    int data;
    struct Node *next;
};

struct Node * createNode(int value)
{
    struct Node *new_node =(struct Node *)malloc(sizeof(struct Node));
    new_node->data=value;
    new_node->next=NULL;
    return new_node;
}

struct Node *insertatfront(struct Node * head, int new_data)
{
    struct Node *new_node=createNode (new_data);
    new_node->next=head;
    return new_node;
}

void insertatend(struct Node *head, int new_data)
{
    struct Node *curr=head;
    struct Node *new_node=createNode(new_data);
    while(curr->next!=NULL)
    curr=curr->next;

    curr->next=new_node;  
}

void printlist(struct Node *head)
{
    struct Node* curr=head;
    while(curr!=NULL)
    {
        printf("%d ",curr->data);
        curr=curr->next;
    }
    printf("\n");
}
 
 int search(struct Node *head, int dat)
 {
    int stat=0;
    struct Node *t=head;
    while(t!=NULL)
    {
        if(t->data==dat)
        {
            stat=1;
            break;
        }
        t=t->next;
    }
    return stat;
 }

 void delete(struct Node **head,int dat)
{
struct Node* temp=*head,*prev;
if(temp!=NULL && temp->data==dat)
{
    *head=temp->next;
    free(temp);
    return;
}
while(temp!=NULL && temp->data!=dat)
{
    prev=temp;
    temp=temp->next;
}
if(temp==NULL)return;
prev->next=temp->next;
free(temp);
}

 void main( void)
 {
    struct Node* head=createNode(2);
    head=insertatfront(head,10);
    insertatend(head,98);
    head=insertatfront(head,20);
    insertatend(head,50);
    printf("Printing the List\n");
    printlist(head);
    printf("After Deleting 20 from the list\n");
    delete(&head,20);
    printlist(head);
    printf("\nSearch Element 20 %s\n",search(head,20)==1?"found":"Not Found");
    printf("Search Element 98 %s\n",search(head,98)==1?"found":"Not Found");
    return ;
 }
 ```
Output:
![image](https://github.com/user-attachments/assets/f7856e3e-3dcd-4695-a058-574b010f819c)




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
```
#include <stdio.h>
#include<stdlib.h>
struct Node
{
    int data;
    struct Node *next;
};

struct Node * createNode(int value)
{
    struct Node *new_node =(struct Node *)malloc(sizeof(struct Node));
    new_node->data=value;
    new_node->next=NULL;
    return new_node;
}

void insertatend(struct Node *head, int new_data)
{
    struct Node *curr=head;
    struct Node *new_node=createNode(new_data);
    while(curr->next!=NULL)
    curr=curr->next;

    curr->next=new_node;  
}

void printlist(struct Node *head)
{
    struct Node* curr=head;
    while(curr!=NULL)
    {
        printf("%d ",curr->data);
        curr=curr->next;
    }
    printf("\n");
}
 

 void delete(struct Node **head,int dat)
{
struct Node* temp=*head,*prev;
if(temp!=NULL && temp->data==dat)
{
    *head=temp->next;
    free(temp);
    return;
}
while(temp!=NULL && temp->data!=dat)
{
    prev=temp;
    temp=temp->next;
}
if(temp==NULL)return;
prev->next=temp->next;
free(temp);
}

 int main()
 {
    struct Node* head=createNode(2);
    insertatend(head,98);
    insertatend(head,50);
    insertatend(head,77);
    printf("Printing the List\n");
    printlist(head);
    printf("After Deleting 20 from the list\n");
    delete(&head,50);
    printlist(head);
    return 0 ;
 }
 ```
Output:
![image](https://github.com/user-attachments/assets/b8551bf3-99ed-4228-83dd-5a88078e4886)


 
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
```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* prev;
    struct Node* next;
};

void display(struct Node* head) {
    struct Node* temp = head;
    
    printf("Doubly Linked List Traversal:\n");
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

struct Node* createNode(int data) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->prev = NULL;
    newNode->next = NULL;
    return newNode;
}

int main() {
    struct Node* head = createNode(10);
    struct Node* second = createNode(20);
    struct Node* third = createNode(30);
    head->next = second;
    second->prev = head;
    second->next = third;
    third->prev = second;

    display(head);

    return 0;
}
```

Output:
![image](https://github.com/user-attachments/assets/56bec92e-fbac-4ccd-81da-9622216cb3b8)



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
```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;
    struct Node* prev;
    struct Node* next;
} *head;


void insert(int value) {
    struct Node* n = (struct Node*)malloc(sizeof(struct Node));
    struct Node* temp = head;

    if (n == NULL) {
        printf("Memory allocation failed.\n");
        return;
    }

    n->data = value;
    n->prev = NULL;
    n->next = NULL;
    if (head == NULL) {
        head = n;
        return;
    }
    while (temp->next != NULL) {
        temp = temp->next;
    }
    temp->next = n;
    n->prev = temp;
}
void display(struct Node* temp) {
    printf("Doubly Linked List:\n");
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}
int main() {
    insert(10);
    insert(20);
    insert(30);
    display(head);

    return 0;
}
```


Output:
![image](https://github.com/user-attachments/assets/31bed201-6a1e-4eaf-9909-0872b55c807c)



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
```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;
    struct Node* next;
}* head ; 

void insert(int value) {
    struct Node* n = (struct Node*)malloc(sizeof(struct Node));
    struct Node* temp = head;
    if (n == NULL) {
        printf("Memory allocation failed.\n");
        return;
    }
    n->data = value;
    n->next = NULL;
    if (head == NULL) {
        head = n;
        return;
    }
    while (temp->next != NULL) {
        temp = temp->next;
    }
    temp->next = n;
}

void delete(int value) {
    struct Node* temp = head;
    struct Node* prev = NULL;
    if (head == NULL) {
        printf("List is empty.\n");
        return;
    }
    if (head->data == value) {
        head = head->next;
        free(temp);
        printf("Element %d deleted.\n", value);
        return;
    }
    while (temp != NULL && temp->data != value) {
        prev = temp;
        temp = temp->next;
    }
    if (temp == NULL) {
        printf("Element %d not found in the list.\n", value);
        return;
    }
    prev->next = temp->next;
    free(temp);
    printf("Element %d deleted.\n", value);
}

void display(struct Node* temp) {
    printf("Linked List: ");
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n\n");
}

int main() {
    insert(10);
    insert(20);
    insert(30);
    insert(40);
    printf("Before Deletion:\n");
    display(head);
    delete(20); 
    delete(40); 
    printf("\nAfter Deletion:\n");
    display(head);
    return 0;
}
```

Output:
![image](https://github.com/user-attachments/assets/5c1f3e73-ef8d-4153-a66a-3d798886582e)






Result:
Thus, the function that deletes a given element from a linked list is verified successfully.





