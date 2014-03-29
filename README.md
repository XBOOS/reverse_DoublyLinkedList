reverse_DoublyLinkedList
========================

this is used to reverse the doubly linked list
#include<stdio.h>
#include<stdlib.h>

//a node of the doubly linked list

struct node{
	int data;//this is the satellite data
	struct node *next; //define the two pointer attribute
	struct node *prev;
};

//function to reverse a doubly linked list
void reverse(struct node **head_ref){//here use the pass by reference so that we can change the head_ref
	
	struct node *temp=NULL;//initialize a node pointer
	struct node *current= *head_ref;
	
	//swap next and prev for all nodes
	while(current!=NULL){
	
		temp=current->prev;//first use temp to refer to one of its neighber
		//then begin to set the 2 pointers
		current->prev=current->next;
		current->next=temp;
		//then change current to next now however the prev points to the next
		current=current->prev;
	}
	//we also need to change head_ref;
	//before changing head, we need to check if the list is empty or list with only one node
	if(temp!=NULL)
	*head_ref = temp-> prev;
	
}
