# kimseonghwan

#include<iostream>
using namespace std;

template<typename T>
void myswap(T& x, T& y) {
	T tmp = x;
	x = y;
	y = tmp;
}

int main() {
	int a, b, c;
	cout << "세 정수 입력: ";
	cin >> a >> b >> c;
	myswap(a, b);
	myswap(b, c);
	cout << "a = " << a << ", b = " << b << ", c = " << c << endl << endl;

	double d, e, f;
	cout << "세 실수 입력: ";
	cin >> d >> e >> f;
	myswap(d, e);
	myswap(e, f);
	cout << "d = " << d << ", e = " << e << ", f = " << f << endl;

	return 0;
}
