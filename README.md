#include <iostream>
using namespace std;

#define MAX 10

class CircularQueue {
    int arr[MAX];
    int front, rear, size;

public:
    CircularQueue() {
        front = -1;
        rear = -1;
        size = 0;
    }

    bool isEmpty() {
        return size == 0;
    }

    bool isFull() {
        return size == MAX;
    }

    void enqueue(int val) {
        if (isFull()) {
            cout << "Queue is full! Cannot enqueue " << val << endl;
            return;
        }
        if (isEmpty()) {
            front = rear = 0;
        } else {
            rear = (rear + 1) % MAX;
        }
        arr[rear] = val;
        size++;
        cout << val << " enqueued successfully.\n";
    }

    void dequeue() {
        if (isEmpty()) {
            cout << "Queue is empty! Cannot dequeue.\n";
            return;
        }
        cout << "Dequeued element: " << arr[front] << endl;
        if (front == rear) {
            front = rear = -1;
        } else {
            front = (front + 1) % MAX;
        }
        size--;
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
        int count = size;
        int i = front;
        while (count--) {
            cout << arr[i] << " ";
            i = (i + 1) % MAX;
        }
        cout << endl;
    }

    void interleave() {
        if (isEmpty()) {
            cout << "Queue is empty. Cannot interleave.\n";
            return;
        }
        if (size % 2 != 0) {
            cout << "Queue size must be even to interleave.\n";
            return;
        }

        int half = size / 2;
        int temp[MAX];
        int i = front;

        for (int k = 0; k < size; k++) {
            temp[k] = arr[i];
            i = (i + 1) % MAX;
        }

        int j = 0, l = half;
        for (int k = 0; k < size; k++) {
            if (k % 2 == 0) {
                arr[(front + k) % MAX] = temp[j++];
            } else {
                arr[(front + k) % MAX] = temp[l++];
            }
        }
        cout << "Queue interleaved successfully.\n";
    }
};

int main() {
    CircularQueue q;
    int choice, val;

    do {
        cout << "\n1. Enqueue\n2. Dequeue\n3. Peek\n4. Display\n5. Is Empty\n6. Is Full\n7. Interleave Queue\n8. Exit\n";
        cout << "Enter choice: ";
        cin >> choice;

        switch (choice) {
            case 1:
                cout << "Enter value to enqueue: ";
                cin >> val;
                q.enqueue(val);
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
                cout << (q.isEmpty() ? "Queue is empty.\n" : "Queue is not empty.\n");
                break;
            case 6:
                cout << (q.isFull() ? "Queue is full.\n" : "Queue is not full.\n");
                break;
            case 7:
                q.interleave();
                break;
            case 8:
                cout << "Exiting...\n";
                break;
            default:
                cout << "Invalid choice. Try again.\n";
        }
    } while (choice != 8);

    return 0;
}


