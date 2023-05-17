# kimseonghwan

#include<iostream>
using namespace std;

template<typename T>


T arr_plus(T arr[], int n) {
	T sum = arr[0];
	for (int i = 1; i < n; i++)
		sum += arr[i];
	return sum;
}

int main() {
	int iarr[] = { 1, 2, 3, 4, 5 };
	double darr[] = { 1.1, 2.2, 3.3 };
	string sarr[] = { "딸기", "바나나", "우유" };

	cout << "정수 배열 합은 " << arr_plus(iarr, 5) << endl;
	cout << "실수 배열 합은 " << arr_plus(darr, 3) << endl;
	cout << "string 배열 경우는 " << arr_plus(sarr, 3) << endl;

}
