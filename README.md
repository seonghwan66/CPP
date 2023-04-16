# kimseonghwan

#include <iostream>
using namespace std;

void myswap(double* a, double* b) {
	double tmp = *a;
	*a = *b;
	*b = tmp;
}

int main() {
	double a, b;
	cout << "두 수 입력 : ";
	cin >> a >> b;
	cout << "(Before) a = " << a << " b = " << b << endl;
	myswap(&a, &b);
	cout << "(After) a = " << a << " b = " << b << endl;
}
