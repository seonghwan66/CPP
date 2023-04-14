# kimseonghwan

#include <iostream>
using namespace std;

void swap(int& x, int& y) {
    int temp = x;
    x = y;
    y = temp;
}

int main() {
    int a, b;
    cout << "두 수 입력 : ";
    cin >> a >> b;
    cout << "(Before) a = " << a << " b = " << b << endl;
    swap(a, b);
    cout << "(After) a = " << a << " b = " << b << endl;
}
