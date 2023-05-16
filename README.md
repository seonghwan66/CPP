# kimseonghwan

#include <iostream>
using namespace std;

// 정수형 배열 합 구하기 함수
int arr_plus(int arr[], int size) {
	int sum = 0;
	for (int i = 0; i < size; i++) {
		sum += arr[i];
	}
	return sum;
}

// 실수형 배열 합 구하기 함수
double arr_plus(double arr[], int size) {
	double sum = 0;
	for (int i = 0; i < size; i++) {
		sum += arr[i];
	}
	return sum;
}

int main() {
	int iarr[] = { 1, 2, 3, 4, 5 };
	double darr[] = { 1.1, 2.2, 3.3 };

	cout << "정수 배열 합은 " << arr_plus(iarr, 5) << endl;
	cout << "실수 배열 합은 " << arr_plus(darr, 3) << endl;

	return 0;
}
