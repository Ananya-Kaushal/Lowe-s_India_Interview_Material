***************************LINKED LIST**************************************
Singly Linked List:-
----------------------------------------------------------------------------

// Definition of a Node in a singly linked list
public class Node {
    
    // Data part of the node
    int data;
    
    // Pointer to the next node in the list
    Node next;

    // Constructor to initialize the node with data
    public Node(int data){
        this.data = data;
        this.next = null;
    }
}

Applications of Linked List:-
------------------------------------------------------------------------------------
<img width="952" height="471" alt="image" src="https://github.com/user-attachments/assets/da5a1b70-f9fc-45f2-91c9-52c5ab9202c4" />
<img width="947" height="466" alt="image" src="https://github.com/user-attachments/assets/1c9409c8-f408-4745-879d-59dfaa712815" />
<img width="950" height="472" alt="image" src="https://github.com/user-attachments/assets/52245129-9171-4ee2-9a54-300e5c875bf0" />
<img width="947" height="475" alt="image" src="https://github.com/user-attachments/assets/34b2d668-16f9-437c-b34b-ae93024fbe77" />

Advantage:-
-----------------------------------------------------------------------------------
Dynamic size (no fixed limit like arrays)
Efficient insertion and deletion (especially in the middle)
Can implement complex data structures like stack, queue, graph

Disadvantage:-
-----------------------------------------------------------------------------------
Extra memory required for storing pointers
No direct/random access (need traversal)
Cache unfriendly (not stored in contiguous memory)

