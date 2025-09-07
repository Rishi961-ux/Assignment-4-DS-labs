#include <iostream>
using namespace std;

#define MAX 5

class Queue {
    int arr[MAX];
    int front, rear;

public:
    Queue() {
        front = -1;
        rear = -1;
    }
      bool isEmpty() {
        return (front == -1 && rear == -1);
    }
      bool isFull() {
        return (rear == MAX - 1);
    }
      void enqueue(int val) {
        if (isFull()) {
            cout << "Queue is full! Cannot enqueue " << val << endl;
            return;
        }
        if (isEmpty()) {
            front = rear = 0;
        } else {
            rear++;
        }
        arr[rear] = val;
        cout << val << " enqueued successfully.\n";
    }
     void dequeue() {
        if (isEmpty()) {
            cout << "Queue is empty! Cannot dequeue.\n";
            return;
        }
        cout << "Dequeued element: " << arr[front] << endl;
        if (front == rear) {
            // Queue has become empty
            front = rear = -1;
        } else {
            front++;
        }
    }
      void peek() {
        if (isEmpty()) {
            cout << "Queue is empty! No front element.\n";
            return;
        }
        cout << "Front element is: " << arr[front] << endl;
    }
     void display() {
        if (isEmpty()) {
            cout << "Queue is empty!\n";
            return;
        }
        cout << "Queue elements: ";
        for (int i = front; i <= rear; i++) {
            cout << arr[i] << " ";
        }
        cout << endl;
    }
};

int main() {
    Queue q;
    int choice, value;
    do {
        cout << "\nQueue Operations Menu:\n";
        cout << "1. Enqueue\n";
        cout << "2. Dequeue\n";
        cout << "3. Peek\n";
        cout << "4. Display\n";
        cout << "5. Check if Empty\n";
        cout << "6. Check if Full\n";
        cout << "7. Exit\n";
        cout << "Enter your choice: ";
        cin >> choice;
        switch (choice) {
            case 1:
                cout << "Enter value to enqueue: ";
                cin >> value;
                q.enqueue(value);
                break;
            case 2:
                q.dequeue();
                break;
            case 3:
                q.peek();
                break;
            case 4:
                q.display();
                break;
            case 5:
                if (q.isEmpty())
                    cout << "Queue is empty.\n";
                else
                    cout << "Queue is not empty.\n";
                break;
            case 6:
                if (q.isFull())
                    cout << "Queue is full.\n";
                else
                    cout << "Queue is not full.\n";
                break;
            case 7:
                cout << "Exiting program.\n";
                break;
            default:
                cout << "Invalid choice. Try again.\n";
        }

    }#include <iostream>
using namespace std;

#define MAX 5

class Queue {
    int arr[MAX];
    int front, rear;

public:
    Queue() {
        front = -1;
        rear = -1;
    }
   bool isEmpty() {
        return (front == -1 && rear == -1);
    }
    bool isFull() {
        return (rear == MAX - 1);
    }
    void enqueue(int val) {
        if (isFull()) {
            cout << "Queue is full! Cannot enqueue " << val << endl;
            return;
        }
        if (isEmpty()) {
            front = rear = 0;
        } else {
            rear++;
        }
        arr[rear] = val;
        cout << val << " enqueued successfully.\n";
    }
     void dequeue() {
        if (isEmpty()) {
            cout << "Queue is empty! Cannot dequeue.\n";
            return;
        }
        cout << "Dequeued element: " << arr[front] << endl;
        if (front == rear) {
            // Queue has become empty
            front = rear = -1;
        } else {
            front++;
        }
    }
    void peek() {
        if (isEmpty()) {
            cout << "Queue is empty! No front element.\n";
            return;
        }
        cout << "Front element is: " << arr[front] << endl;
    }
    void display() {
        if (isEmpty()) {
            cout << "Queue is empty!\n";
            return;
        }
        cout << "Queue elements: ";
        for (int i = front; i <= rear; i++) {
            cout << arr[i] << " ";
        }
        cout << endl;
    }
};

int main() {
    Queue q;
    int choice, value;
    do {
        cout << "\nQueue Operations Menu:\n";
        cout << "1. Enqueue\n";
        cout << "2. Dequeue\n";
        cout << "3. Peek\n";
        cout << "4. Display\n";
        cout << "5. Check if Empty\n";
        cout << "6. Check if Full\n";
        cout << "7. Exit\n";
        cout << "Enter your choice: ";
        cin >> choice;
        switch (choice) {
            case 1:
                cout << "Enter value to enqueue: ";
                cin >> value;
                q.enqueue(value);
                break;
            case 2:
                q.dequeue();
                break;
            case 3:
                q.peek();
                break;
            case 4:
                q.display();
                break;
            case 5:
                if (q.isEmpty())
                    cout << "Queue is empty.\n";
                else
                    cout << "Queue is not empty.\n";
                break;
            case 6:
                if (q.isFull())
                    cout << "Queue is full.\n";
                else
                    cout << "Queue is not full.\n";
                break;
            case 7:
                cout << "Exiting program.\n";
                break;
            default:
                cout << "Invalid choice. Try again.\n";
        }

    } while (choice != 7);

    return 0;
}
while (choice != 7);

    return 0;
}
