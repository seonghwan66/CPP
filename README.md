# kimseonghwan

#include <iostream>
using namespace std;

int main() {

	int n;
	cout << "입력할 정수의 개수 : " << endl;
	cin >> n;

	if (n <= 0) {
	cout << "양수를 입력하세요.";
	return 0;
	}
	int *p = new int[n];

	if (p == NULL) {
		cout << "메모리를 할당할 수 없습니다.";
		return 0;
	}
	cout << n << "개의 정수를 입력하세요.\n";
	for (int i = 0; i < n; i++)
		cin >> p[i];

	cout << "거꾸로 하면 다음과 같습니다.\n";
	for (int i = n-1; i >= 0; --i)
		cout << p[i] << ' ';

	cout << endl;
	delete [] p;
}
