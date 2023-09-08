package LinkedList;

class CircNode {
    int data;
    CircNode next;

    public CircNode(int data) {
        this.data = data;
        this.next = null;
    }
}

class CircMethods {
    CircNode head;

    public CircMethods() {
        head = null;
    }

    void insert(int data) {
        CircNode newNode = new CircNode(data);
        if (head == null) {
            head = newNode;
            head.next = head; // Pointing to itself for a single node circular list.
        } else {
            CircNode temp = head;
            while (temp.next != head) {
                temp = temp.next;
            }
            
            temp.next = newNode;
            newNode.next = head;
            head=newNode;
        }
    }

    void insertAtEnd(int data) {
        CircNode newNode = new CircNode(data);
        if (head == null) {
            head = newNode;
            head.next = head; // Pointing to itself for a single node circular list.
        } else {
            CircNode temp = head;
            while (temp.next != head) {
                temp = temp.next;
            }
            temp.next = newNode;
            newNode.next = head; // Make the new node point back to the head.
        }
    }

    

    void insertAtPosition(int pos, int data) {
        if (pos <= 0) {
            insert(data);
        } else {
            CircNode newNode = new CircNode(data);
            if (head == null) {
                head = newNode;
                head.next = head; // Pointing to itself for a single node circular list.
            } else {
                CircNode temp = head;
                for (int i = 1; i < pos; i++) {
                    temp = temp.next;
                    if (temp == head) {
                        System.out.println("Invalid position");
                        return;
                    }
                }
                newNode.next = temp.next;
                temp.next = newNode;
            }
        }
    }

    void deleteAtBeginning() {
        if (head == null) {
            System.out.println("List is empty.");
            return;
        }

        CircNode temp = head;
        while (temp.next != head) {
            temp = temp.next;
        }

        if (temp == head) {
            head = null;
        } else {
            temp.next = head.next;
            head = head.next;
        }
    }

    void deleteAtPosition(int pos) {
        if (pos <= 0 || head == null) {
            deleteAtBeginning();
        } else {
            CircNode temp = head;
            CircNode prev = null;
            for (int i = 1; i <= pos; i++) {
                prev = temp;
                temp = temp.next;
                if (temp == head) {
                    System.out.println("Invalid position");
                    return;
                }
            }
            prev.next = temp.next;
        }
    }

    void display() {
        if (head == null) {
            System.out.println("List is empty.");
            return;
        }

        CircNode temp = head;
        do {
            System.out.print(temp.data + " ");
            temp = temp.next;
        } while (temp != head);
        System.out.println();
    }
}

public class CircLinkedList extends CircMethods {
    public static void main(String[] args) {
        CircLinkedList list = new CircLinkedList();
        System.out.println("insertion at begaining");
        list.insert(5);
        list.insert(9);
        list.insert(10);
        list.display();
        System.out.println("insertion at end");
        list.insertAtEnd(15);
        list.display();
        System.out.println("insertion at position");
        list.insertAtPosition(2, 7);
        list.display();
        System.out.println("deletion at begainig");
        list.deleteAtBeginning();
        list.display();
        System.out.println("deletion at position");
        list.deleteAtPosition(2);
        list.display();
    }
}
