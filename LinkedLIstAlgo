using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

//this is modified by rabin gora

namespace CSC340._515_SLL
{
    class Program
    {
        static void Main(string[] args)
        {
            Node myNode = new Node(8);//this is how we create a new node
            Node myNode2 = new Node(2);

            SinglyLinkedList myList = new SinglyLinkedList();//creates an empty list
            //Console.WriteLine(myList.isEmpty());
            //myList.addFront(1);
            myList.addFront(2);
            //myList.addFront(3);
            //myList.print();

            Console.WriteLine();
            Console.WriteLine();
            myList.addBack(10);
            myList.addBack(20);
            myList.addBack(30);
            myList.insert(14);
            myList.insert(32);
            myList.insert(9);
            myList.print();

            Console.WriteLine();
        }

        public class Node
        {
            //data
            public int data;
            public Node next;

            //methods
            //constructors
            public Node(int newVal)
            {
                data = newVal;
                next = null;
            }
        }

        public class SinglyLinkedList
        {
            //data
            Node head;

            //methods
            public void print()  //O(n)
            {
                if (isEmpty())
                {
                    Console.WriteLine("the list is empty!");
                }
                else
                {
                    Node current = head;
                    while (current != null)
                    {
                        Console.Write(current.data + " "); //display the value
                        current = current.next;         //move next
                    }
                }
            }

            public void insert(int newValue) //assumes the list is sorted
            {
                if(isEmpty())
                {
                    addFront(newValue);
                }
                else if(newValue<=head.data)
                {
                    addFront(newValue);
                }
                else
                {
                    //create a new node
                    Node newNode = new Node(newValue);

                    Node current = head;

                    while (current.next!= null && current.next.data < newValue)
                        current = current.next;//move right

                    //link in the new node ... current now point to the node with largest value less than newValue
                    newNode.next = current.next;
                    current.next = newNode;
                }
            }
            public void append(int newVal)//append is now an "alias" of addBack
            {
                addBack(newVal);
            }

            public void addBack(int newVal)//O(n)
            {
                //create a new node
                Node newNode = new Node(newVal);

                if (isEmpty())
                {
                    head = newNode;
                }
                else
                {
                    //find the last nonempty node ...
                    Node curr = head;
                    while (curr.next != null)
                        curr = curr.next;//move ahead

                    //link the last node to the newnode
                    curr.next = newNode;
                }
            }
            public void deleteBack()//O(n)
            {
                if(isEmpty())
                {
                    Console.WriteLine("FATAL ERROR!!!! cannot delete the last node of an empty list!");
                }
                else if (head.next==null)//we only have one node in the lisr
                {
                    head = null;
                }
                else //we have at least two nodes
                {
                    Node curr = head;
                    while (curr.next.next != null)
                        curr = curr.next;
                    curr.next = null;
                }
            }
            public void deleteFront()//O(1)
            {
                if(isEmpty())
                {
                    Console.WriteLine("FATAL ERROR!!!! cannot delete the head of an empty list!");
                }
                else
                {
                    head = head.next;
                }   
            }
            public void addFront(int newVal) //O(1)
            {
                //create a new node
                Node newNode = new Node(newVal);

                //link the new node to the list
                newNode.next = head;

                //reset the head
                head = newNode;
            }
            public bool isEmpty() //O(1)
            {
                //if (head == null)
                //    return true;
                //else
                //    return false;
                return head == null;
            }

            //constructor
            public SinglyLinkedList()
            {
                head = null;
            }
        }
    }
}
