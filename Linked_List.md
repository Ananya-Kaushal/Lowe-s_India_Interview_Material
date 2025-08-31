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

Ques 4)Find Length of Linked List?

Solution):-

class Node{
    int data;
    Node next;
    Node(int a){  data = a; next = null; }
}

class Solution {
    public int getCount(Node head) {
        // code here
        int length=0;
        Node temp=head;
        while(temp != null)
        {
            length++;
            temp=temp.next;
        }
        
        return length;
    }
}

Ques 5)Search in Linked List?

Solution):-

class Node {
   int data;
    Node next;

    Node(int d)  { data = d;  next = null; }
}
class Solution {
    public boolean searchKey(Node head, int key) {
        // Code here
        Node temp=head;
        while(temp != null)
        {
            if(temp.data==key)return true;
            temp=temp.next;
        }
        
        return false;
    }
}

Ques 6)Delete the Head of the Linked List?

Solution):-

class Node
{
    int data;
    Node next;

    Node(int d)
    {
        this.data = d;
        this.next = null;
    }
}
class Solution {
    Node deleteHeadNode(Node head) {
        // code here
        if(head == null)return null;
        head=head.next;
        return head;
    }
}

Ques 7)Delete the last Element in the Linked List?

Solution):-

class Node
{
    int data;
    Node next;

    Node(int d)
    {
        this.data = d;
        this.next = null;
    }
}
class Solution {
    Node deleteNode(Node head, int x) {
        // code here
        
        //Delete the last element in L.L.
        if(head == null || head.next==null)return null;
        Node temp=head;
        while(temp.next.next != null)
        {
            temp=temp.next;
        }
        temp.next=null;
        return head;
    }
}

Ques 8)Delete a Node in Linked List as Position of that Node is Given?

TYPE 1):-

Input: Head Node = 8(8 -> 2 -> 3 -> 1 -> 7), x = 1,
    
Output: 2 -> 3 -> 1 -> 7
Explanation: After deleting the node at the 1st position (1-base indexing), the linked list is as
    

Solution):-

class Node
{
    int data;
    Node next;

    Node(int d)
    {
        this.data = d;
        this.next = null;
    }
}
class Solution {
    Node deleteNode(Node head, int x) {
        // code here
        if(head == null)return null;
        
        if(x == 1)//Delete the head of L.L.
        {
            head=head.next;
            return head;
        }
        
        Node temp=head;
        Node prev=null;
        int cnt=0;
        
        while(temp != null)
        {
            cnt++;
            if(cnt == x)
            {
                prev.next=prev.next.next;
                break;
            }
            prev=temp;
            temp=temp.next;
        }
        
        return head;
    }
}

//T.C:-O(k)

Ques 9)Delete a Node in Linked List as Value(data) of that Node is Given?

TYPE 2):-

Input: Head Node = 8(8 -> 2 -> 3 -> 1 -> 7), x = 1,
    
Output: 8 -> 2 -> 3 -> 7

Solution):-

public class ListNode {
    int val;
    ListNode next;
    ListNode() {}
    ListNode(int val) { this.val = val; }
    ListNode(int val, ListNode next) { this.val = val; this.next = next; }
  }

  public ListNode deleteNode(ListNode head ,int x)
    {

        if(head == null)return head;

        if(head.val == x)
        {
            head=head.next;
            return head;
        }

        ListNode temp=head;
        ListNode prev=null;

        while(temp != null)
        {
            if(temp.val == x)
            {
                prev.next = prev.next.next;
            }
            prev=temp;
            temp=temp.next;
        }
        return head;
    }

    //T.C.:- O(n) where n is the length of the L.L.

Ques 10)Insert at the head a nee node?

Input: LinkedList = 1->2->4 , x = 3
Output: 3->1->2->4
Explanation: The new element is inserted after the Head element in the linked list.

Solution):-

class Node {
    int data;
    Node next;

    public Node(int data){
        this.data = data;
        this.next = null;
    }
}

class Solution {
    public Node insertInMiddle(Node head, int x) {
        // Code here
        Node temp=new Node(x,head);
        return temp;
    }
}
