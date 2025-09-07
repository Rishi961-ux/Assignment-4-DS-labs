#include <iostream>
#include <queue>
using namespace std;

class StackUsingOneQueue {
    queue<int> q;

public:
    void push(int x) {
        q.push(x);
        int size = q.size();
        while (size-- > 1) {
            q.push(q.front());
            q.pop();
        }
    }

    void pop() {
        if (!q.empty()) q.pop();
    }

    int top() {
        return q.empty() ? -1 : q.front();
    }

    bool empty() {
        return q.empty();
    }
};

int main() {
    StackUsingOneQueue s;
    s.push(10);
    s.push(20);
    cout << s.top() << "\n";
    s.pop();
    cout << s.top() << "\n";
    s.pop();
    cout << (s.empty() ? "Empty" : "Not empty") << "\n";
}
