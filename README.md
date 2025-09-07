#include <iostream>
#include <queue>
#include <unordered_map>
using namespace std;

int main() {
    string s;
    cout << "Enter string (space separated characters): ";
    getline(cin, s);

    queue<char> q;
    unordered_map<char, int> freq;

    for (char c : s) {
        if (c == ' ') continue;
        freq[c]++;
        q.push(c);

        while (!q.empty() && freq[q.front()] > 1) {
            q.pop();
        }

        if (!q.empty())
            cout << q.front() << " - " << freq[q.front()] << "\n";
        else
            cout << "-1\n";
    }

    return 0;
}

