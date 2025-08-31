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

    public Node(int data1,Node node)
    {
        this.data=data1;
        this.next=node;
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
Dynamic size (no fixed limit like arrays).

Efficient insertion and deletion (especially in the middle).

Can implement complex data structures like stack, queue, graph.

Disadvantage:-
-----------------------------------------------------------------------------------
Extra memory required for storing pointers.

No direct/random access (need traversal).

Cache unfriendly (not stored in contiguous memory).

MEMORY USAGE:-
-----------------------------------------------------------------------------------
In 32 Bits:-
-----------------
Integer:- 4 bytes
pointer:- 4 bytes
------------------
Total:- 8 bytes
------------------

In 64 Bits:-
-------------------
Integer:- 4 bytes
pointer:- 8 bytes
-------------------
Total:- 12 bytes
-------------------

Ques 1)Array to a Linked List?

Solution):-

class Node {
    int data;
    Node next;

    Node (int d, Node next) {
       this.data = d;
       this.next = next;
    }
    Node (int d) {
       this.data = d;
       this.next = null;
    }
};
class Solution {
    public Node arrayToList(int arr[]) {
        // code here
        int n=arr.length;
        Node head=new Node(arr[0]);
        Node mover=head;
        
        for(int i=1;i<n;i++)
        {
            Node temp=new Node(arr[i]);
            mover.next=temp;
            mover=temp;
        }
        
        return head;
    }
}

Ques 2)Traverse a Linked List?

Solution):-
class Node {
    int data;
    Node next;
    Node(int x) {
        data = x;
        next = null;
    }
}

class Solution {
    public ArrayList<Integer> printList(Node head) {
        // code here
        Node temp=head;
        while(temp != null)
        {
            System.out.println(temp.data);
            temp=temp.next;
        }
    }
}

Ques 3)Print a Linked List using ArrayList?

Solution):-

class Node {
    int data;
    Node next;
    Node(int x) {
        data = x;
        next = null;
    }
}

class Solution {
    public ArrayList<Integer> printList(Node head) {
        // code here
        Node temp=head;
        ArrayList<Integer> arr=new ArrayList<>();
        while(temp != null)
        {
            arr.add(temp.data);
            temp=temp.next;
        }
        return arr;
    }
}
