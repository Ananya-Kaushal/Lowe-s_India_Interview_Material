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

Solution 1):-

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

Solution 2)Here we are also printing the Linked List

class Node 
{ 
    int data; 
    Node next;
    Node (int d, Node next) 
    { 
        this.data = d; 
        this.next = next; 
        
    } 
    Node (int d) 
    { 
        this.data = d; 
        this.next = null; 
        
    } 
    
}; 
class Main 
{ 
    public static void main(String[] args) 
    { 
        System.out.println("Try programiz.pro"); 
        int arr[]={1, 2, 4, 3, 8, 6}; 
        Node head=arrayToList(arr); 
        printLinkedList(head); 
        
    }
    public static Node arrayToList(int arr[]) 
    { // code here 
    
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
        
    public static void printLinkedList(Node head)
    {
        Node temp=head;
        while(temp != null)
        {
            if(temp.next != null)System.out.print(temp.data+"->");
            else
            {
                System.out.print(temp.data);
            }
            temp=temp.next;
        }
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

Ques 11)Insert the new node at last of the Linked List?

Input: LinkedList = 1->2->4 , x = 3
Output: 1->2->4->3
Explanation: The new element is inserted at the end of linked list.

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
        
        if(head == null)
        {
            return new Node(x);
        }
        
        Node temp=head;
        Node m=new Node(x);
        while(temp.next != null)
        {
            temp=temp.next;
        }
        
        temp.next=m;
        return head;
    }
}

Ques 12) Insert in the Linked List the element at a given postion?

Solution):-

class Node { int data; Node next;

Node (int d, Node next) {
   this.data = d;
   this.next = next;
}
Node (int d) {
   this.data = d;
   this.next = null;
}
}; 
class Main {
    public static void main(String[] args) {
        System.out.println("Try programiz.pro");
        int arr[]={1, 2, 4, 3, 8, 6};
        Node head=arrayToList(arr);
        printLinkedList(head);
        Node insertion=insertAtK(head, 10, 4);
        printLinkedList(insertion);
    }
    
    public static Node arrayToList(int arr[]) 
    { // code here 
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
    
    public static void printLinkedList(Node head)
    {
        Node temp=head;
        while(temp != null)
        {
            if(temp.next != null)System.out.print(temp.data+"->");
            else
            {
                System.out.print(temp.data);
            }
            temp=temp.next;
        }
        System.out.println();
    }
    
    public static Node insertAtK(Node head, int el,int k)
    {
        if(head == null)
        {
            if(k==1)
            return new Node(el);
            
            else{
                return null;
            }
        }
        
        if(k == 1)
        {
            Node temp=new Node(el,head);
            return temp;
        }
        
        int cnt=0;
        Node temp=head;
        while(temp != null)
        {
            cnt++;
            if(cnt == k-1)
            {
                Node m=new Node(el);
                Node nextpointer = temp.next;
                temp.next=m;
                m.next=nextpointer;
                break;
            }
            temp=temp.next;
        }
        return head;
    }
}

Ques 13)Insert an Element before the value Val?

Solution):-

class Node { int data; Node next;

Node (int d, Node next) {
   this.data = d;
   this.next = next;
}
Node (int d) {
   this.data = d;
   this.next = null;
}
}; 
class Main {
    public static void main(String[] args) {
        System.out.println("Try programiz.pro");
        int arr[]={1, 2, 4, 3, 8, 6};
        Node head=arrayToList(arr);
        printLinkedList(head);
        Node insertion=insertAtK(head, 10, 4);
        printLinkedList(insertion);
        Node insertB=insertBeforeValue(head , 17, 8);
        printLinkedList(insertB);
    }
    
    public static Node arrayToList(int arr[]) 
    { // code here 
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
    
    public static void printLinkedList(Node head)
    {
        Node temp=head;
        while(temp != null)
        {
            if(temp.next != null)System.out.print(temp.data+"->");
            else
            {
                System.out.print(temp.data);
            }
            temp=temp.next;
        }
        System.out.println();
    }
    
    public static Node insertBeforeValue(Node head, int el, int val)
    {
        if(head == null)
        {
            return null;
        }
        
        if(head.data == val)
        {
            Node temp=new Node(el,head);
            return temp;
        }
        
        Node temp=head;
        while(temp != null)
        {
            if(temp.next.data == val)
            {
                // Node m=new Node(el,temp.next);
                // temp.next=m;
                // break;
                Node m=new Node(el);
                Node p=temp.next;
                temp.next=m;
                m.next=p;
                break;
            }
            temp=temp.next;
        }
        return head;
    }
}

Ques 14)Array to Doubly Linked List and then Printing Doubly Linked List?

Solution):-

class Node
{
    int data;
    Node next;
    Node prev;
    
    Node(int data, Node next, Node prev)
    {
        this.data=data;
        this.next=next;
        this.prev=prev;
    }
    
    Node(int data)
    {
        this.data=data;
        this.next=next;
        this.prev=prev;
    }
}
class Main 
{
    public static void main(String[] args) {
        System.out.println("Try programiz.pro");
        int arr[]={1, 2, 4, 3, 8, 6}; 
        Node head=arrayToList(arr); 
        printLinkedList(head);

    }
    public static Node arrayToList(int arr[]) 
    { // code here 
    
          int n=arr.length; 
          Node head=new Node(arr[0]); 
          Node prev=head;
    
        for(int i=1;i<n;i++)
        {
            Node temp=new Node(arr[i],null,prev);
            prev.next=temp;
            prev=temp;
        }
    
        return head;
    }
        
    public static void printLinkedList(Node head)
    {
        Node temp=head;
        while(temp != null)
        {
            if(temp.next != null)System.out.print(temp.data+"->");
            else
            {
                System.out.print(temp.data);
            }
            temp=temp.next;
        }
        System.out.println();
    }
}

Ques 15)Delete the Head of the Doubly Linked List?

Solution):-

class Node
{
    int data;
    Node next;
    Node prev;
    
    Node(int data, Node next, Node prev)
    {
        this.data=data;
        this.next=next;
        this.prev=prev;
    }
    
    Node(int data)
    {
        this.data=data;
        this.next=next;
        this.prev=prev;
    }
}
class Main 
{
    public static void main(String[] args) {
        System.out.println("Try programiz.pro");
        int arr[]={1, 2, 4, 3, 8, 6}; 
        Node head=arrayToList(arr); 
        printLinkedList(head);
        Node removeHead=removeHeadOfDLL(head);
        printLinkedList(removeHead);

    }
    public static Node arrayToList(int arr[]) 
    { // code here 
    
          int n=arr.length; 
          Node head=new Node(arr[0]); 
          Node prev=head;
    
        for(int i=1;i<n;i++)
        {
            Node temp=new Node(arr[i],null,prev);
            prev.next=temp;
            prev=temp;
        }
    
        return head;
    }
    
    public static Node removeHeadOfDLL(Node head)
    {
        // Node temp=head.next;
        // head.next=null;
        // temp.prev=null;
        // return temp;

        Node back=head;
        head=head.next;
        
        head.prev=null;
        back.next=null;
        
        return head;
    }
        
    public static void printLinkedList(Node head)
    {
        Node temp=head;
        while(temp != null)
        {
            if(temp.next != null)System.out.print(temp.data+"->");
            else
            {
                System.out.print(temp.data);
            }
            temp=temp.next;
        }
        System.out.println();
    }
}

Ques 16)Delete Tail of Doubly Linked List?

Solution):-

class Node
{
    int data;
    Node next;
    Node prev;
    
    Node(int data, Node next, Node prev)
    {
        this.data=data;
        this.next=next;
        this.prev=prev;
    }
    
    Node(int data)
    {
        this.data=data;
        this.next=next;
        this.prev=prev;
    }
}

class Main 
{
    public static void main(String[] args) 
    {
        System.out.println("Try programiz.pro");
        int arr[]={1, 2, 4, 3, 8, 6}; 
        Node head=arrayToList(arr); 
        printLinkedList(head); 
        Node removeTail = deleteTail(head);
        printLinkedList(removeTail);
    }
    
    public static Node arrayToList(int arr[]) 
    { // code here 
    
        int n=arr.length; 
        Node head=new Node(arr[0]); 
        Node prev=head;
        
        for(int i=1;i<n;i++)
        {
            Node temp=new Node(arr[i],null,prev);
            prev.next=temp;
            prev=temp;
        }
        
        return head;
    }
    
    public static void printLinkedList(Node head)
    {
        Node temp=head;
        while(temp != null)
        {
            if(temp.next != null)System.out.print(temp.data+"->");
            else
            {
                System.out.print(temp.data);
            }
            temp=temp.next;
        }
        System.out.println();
    }
    
    public static Node deleteTail(Node head)
    {
        if(head == null || head.next == null)
        {
            return null;
        }
        
        Node tail=head;
        
        while(tail.next != null)
        {
            tail=tail.next;
        }
        
        Node back=tail.prev;
        back.next=null;
        tail.prev=null;
        
        return head;
    }

}

Ques 17)Delete Kth Node in Doubly Linked List?

Solution):-

class Node
{
    int data;
    Node next;
    Node prev;
    
    Node(int data, Node next, Node prev)
    {
        this.data=data;
        this.next=next;
        this.prev=prev;
    }
    
    Node(int data)
    {
        this.data=data;
        this.next=next;
        this.prev=prev;
    }
}
class Main {
    public static void main(String[] args) {
        System.out.println("Try programiz.pro");
        int arr[]={1, 2, 4, 3, 8, 6}; 
        Node head=arrayToList(arr); 
        printLinkedList(head); 
        Node removeKNode =deleteKthNode(head, 3);
        printLinkedList(removeKNode);
    }
    
    public static Node arrayToList(int arr[]) 
    { // code here 
    
        int n=arr.length; 
        Node head=new Node(arr[0]); 
        Node prev=head;
        
        for(int i=1;i<n;i++)
        {
            Node temp=new Node(arr[i],null,prev);
            prev.next=temp;
            prev=temp;
        }
        
        return head;
    }
    
    public static void printLinkedList(Node head)
    {
        Node temp=head;
        while(temp != null)
        {
            if(temp.next != null)System.out.print(temp.data+"->");
            else
            {
                System.out.print(temp.data);
            }
            temp=temp.next;
        }
        System.out.println();
    }
    
    public static Node deleteTail(Node head)
    {
        if(head == null || head.next == null)
        {
            return null;
        }
        
        Node tail=head;
        
        while(tail.next != null)
        {
            tail=tail.next;
        }
        
        Node back=tail.prev;
        back.next=null;
        tail.prev=null;
        
        return head;
    }
    
    public static Node deleteHead(Node head)
    {
        if(head == null || head.next == null)
        {
            return null;
        }
        
        Node temp=head;
        temp=temp.next;
        temp.prev=null;
        head.next=null;
        
        return temp;
    }
    
    public static Node deleteKthNode(Node head, int k)
    {
        if(head == null)
        {
            return null;
        }
        
        Node temp=head;
        int cnt=0;
        while(temp != null)
        {
            cnt++;
            if(cnt == k)break;
            temp=temp.next;
        }
        
        Node back=temp.prev;
        Node front=temp.next;
        
        if(back == null && front == null)//Single which has to be deleted from the D.L.L.
        {
            return null;
        }
        
        else if(back == null)
        {
            deleteHead(temp);
        }
        
        else if(front == null)
        {
            deleteTail(temp);
        }
        
        back.next =front;
        front.prev=back;
        
        temp.next=null;
        temp.prev=null;
        
        return head;
    }
}

Ques 18) Delete Node with n as data in Doubly Linked List?

Solution):-

class Node
{
    int data;
    Node next;
    Node prev;
    
    Node(int data, Node next, Node prev)
    {
        this.data=data;
        this.next=next;
        this.prev=prev;
    }
    
    Node(int data)
    {
        this.data=data;
        this.next=next;
        this.prev=prev;
    }
}
class Main {
    public static void main(String[] args) {
        System.out.println("Try programiz.pro");
        int arr[]={1, 2, 4, 3, 8, 6}; 
        Node head=arrayToList(arr); 
        printLinkedList(head); 
        Node removeKNode =deleteNode(head, 3);
        printLinkedList(removeKNode);
    }
    
    public static Node arrayToList(int arr[]) 
    { // code here 
    
        int n=arr.length; 
        Node head=new Node(arr[0]); 
        Node prev=head;
        
        for(int i=1;i<n;i++)
        {
            Node temp=new Node(arr[i],null,prev);
            prev.next=temp;
            prev=temp;
        }
        
        return head;
    }
    
    public static void printLinkedList(Node head)
    {
        Node temp=head;
        while(temp != null)
        {
            if(temp.next != null)System.out.print(temp.data+"->");
            else
            {
                System.out.print(temp.data);
            }
            temp=temp.next;
        }
        System.out.println();
    }
    
    public static Node deleteTail(Node head)
    {
        if(head == null || head.next == null)
        {
            return null;
        }
        
        Node tail=head;
        
        while(tail.next != null)
        {
            tail=tail.next;
        }
        
        Node back=tail.prev;
        back.next=null;
        tail.prev=null;
        
        return head;
    }
    
    public static Node deleteHead(Node head)
    {
        if(head == null || head.next == null)
        {
            return null;
        }
        
        Node temp=head;
        temp=temp.next;
        temp.prev=null;
        head.next=null;
        
        return temp;
    }
    
    public static Node deleteNode(Node head, int n)
    {
        if(head == null)
        {
            return null;
        }
        
        Node temp=head;
        while(temp != null)
        {
            if(temp.data == n)break;
            temp=temp.next;
        }
        
        Node back=temp.prev;
        Node front=temp.next;
        
        if(back == null && front == null)
        {
            return head;
        }
        
        else if(back == null)
        {
            deleteHead(head);
        }
        
        else if(front == null)
        {
            deleteTail(head);
        }
        
        back.next=front;
        front.prev=back;
        
        temp.next=null;
        temp.prev=null;
        
        return head;
    }
}

Ques 19) Delete a given Node from Doubly Linked List?

Solution):- 

Remember:-Using this Function Head Node can not be deleted.

class Node
{
    int data;
    Node next;
    Node prev;
    
    Node(int data, Node next, Node prev)
    {
        this.data=data;
        this.next=next;
        this.prev=prev;
    }
    
    Node(int data)
    {
        this.data=data;
        this.next=next;
        this.prev=prev;
    }
}
class Main {
    public static void main(String[] args) {
        System.out.println("Try programiz.pro");
        int arr[]={1, 2, 4, 3, 8, 6}; 
        Node head=arrayToList(arr); 
        printLinkedList(head); 
        // Node removeKNode =deleteNode(head, 3);
        // printLinkedList(removeKNode);
        deleteNode(head.next.next);
        printLinkedList(head);
    }
    
    public static Node arrayToList(int arr[]) 
    { // code here 
    
        int n=arr.length; 
        Node head=new Node(arr[0]); 
        Node prev=head;
        
        for(int i=1;i<n;i++)
        {
            Node temp=new Node(arr[i],null,prev);
            prev.next=temp;
            prev=temp;
        }
        
        return head;
    }
    
    public static void printLinkedList(Node head)
    {
        Node temp=head;
        while(temp != null)
        {
            if(temp.next != null)System.out.print(temp.data+"->");
            else
            {
                System.out.print(temp.data);
            }
            temp=temp.next;
        }
        System.out.println();
    }
    
    public static Node deleteTail(Node head)
    {
        if(head == null || head.next == null)
        {
            return null;
        }
        
        Node tail=head;
        
        while(tail.next != null)
        {
            tail=tail.next;
        }
        
        Node back=tail.prev;
        back.next=null;
        tail.prev=null;
        
        return head;
    }
    
    public static Node deleteHead(Node head)
    {
        if(head == null || head.next == null)
        {
            return null;
        }
        
        Node temp=head;
        temp=temp.next;
        temp.prev=null;
        head.next=null;
        
        return temp;
    }
    
    public static void deleteNode(Node temp)
    {
        Node back=temp.prev;
        Node front=temp.next;
        
        if(front == null)
        {
            back.next=null;
            front.prev=null;
            
            return;
        }
        
        back.next=front;
        front.prev=back;
        
        temp.prev=null;
        temp.next=null;
    }
}

Output:-
Try programiz.pro
1->2->4->3->8->6
1->2->3->8->6

Ques 20)Insert Before Head of Doubly Linked List?

Solution):-

class Node
{
    int data;
    Node next;
    Node prev;
    
    Node(int data, Node next, Node prev)
    {
        this.data=data;
        this.next=next;
        this.prev=prev;
    }
    
    Node(int data)
    {
        this.data=data;
        this.next=next;
        this.prev=prev;
    }
}
class Main {
    public static void main(String[] args) {
        System.out.println("Try programiz.pro");
        int arr[]={1, 2, 4, 3, 8, 6}; 
        Node head=arrayToList(arr); 
        printLinkedList(head); 
        Node insertBHead =insertBeforeHead(head, 9);
        printLinkedList(insertBHead);
    }
    
    public static Node arrayToList(int arr[]) 
    { // code here 
    
        int n=arr.length; 
        Node head=new Node(arr[0]); 
        Node prev=head;
        
        for(int i=1;i<n;i++)
        {
            Node temp=new Node(arr[i],null,prev);
            prev.next=temp;
            prev=temp;
        }
        
        return head;
    }
    
    public static void printLinkedList(Node head)
    {
        Node temp=head;
        while(temp != null)
        {
            if(temp.next != null)System.out.print(temp.data+"->");
            else
            {
                System.out.print(temp.data);
            }
            temp=temp.next;
        }
        System.out.println();
    }
    
    public static Node insertBeforeHead(Node head, int val)
    {
        Node newHead = new Node(val,head,null);
        // newHead.prev=null;
        
        head.prev=newHead;
        
        return newHead;
    }
    
}

Output:-
Try programiz.pro
1->2->4->3->8->6
9->1->2->4->3->8->6

Ques 21) Insert After the Head in Doubly Linked List?

Solution):-

class Node
{
    int data;
    Node next;
    Node prev;
    
    Node(int data, Node next, Node prev)
    {
        this.data=data;
        this.next=next;
        this.prev=prev;
    }
    
    Node(int data)
    {
        this.data=data;
        this.next=next;
        this.prev=prev;
    }
}
class Main {
    public static void main(String[] args) {
        System.out.println("Try programiz.pro");
        int arr[]={1, 2, 4, 3, 8, 6}; 
        Node head=arrayToList(arr); 
        printLinkedList(head); 
        Node insertAHead =insertAfterHead(head, 9);
        printLinkedList(insertAHead);
    }
    
    public static Node arrayToList(int arr[]) 
    { // code here 
    
        int n=arr.length; 
        Node head=new Node(arr[0]); 
        Node prev=head;
        
        for(int i=1;i<n;i++)
        {
            Node temp=new Node(arr[i],null,prev);
            prev.next=temp;
            prev=temp;
        }
        
        return head;
    }
    
    public static void printLinkedList(Node head)
    {
        Node temp=head;
        while(temp != null)
        {
            if(temp.next != null)System.out.print(temp.data+"->");
            else
            {
                System.out.print(temp.data);
            }
            temp=temp.next;
        }
        System.out.println();
    }
    
    public static Node insertAfterHead(Node head, int val)
    {
        Node front=head.next;
        Node temp=new Node(val);
        
        head.next=temp;
        front.prev=temp;
        
        temp.prev=head;
        temp.next=front;
        
        return head;
    }
}

Output:-
Try programiz.pro
1->2->4->3->8->6
1->9->2->4->3->8->6
