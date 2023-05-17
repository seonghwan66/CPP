# kimseonghwan

#include<iostream>
using namespace std;

template<typename T>
T sum(T a, T b, T c = 0) {
	return a + b + c;
}

int main() {
	cout << "두 수의 합은 " << sum<int>(5, 7) << endl;
	cout << "세 수의 합은 " << sum<int>(5, 7, 8) << endl;
	cout << "세 실수의 합은 " << sum<double>(3.14, 7.99, -1.0) << endl;
}
