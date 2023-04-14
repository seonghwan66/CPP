# kimseonghwan

#include <iostream>
using namespace std;

void swap(int* a, int* b) {
	int check = *a;
	*a = *b;
	*b = check;
}
int main() {
	int a, b;
	cout << "두 수 입력 : ";
		cin >> a >> b;
		cout << "(Before) a = " << a << " b = " << b << endl;
		swap(&a, &b);
		cout << "(After) a = " << a << " b = " << b << endl;
}
