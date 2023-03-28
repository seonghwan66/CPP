# kimseonghwan

#include <iostream>
using namespace std;

int main() {
	int X, N, a, b;
	cin >> X;
	cin >> N;
	int sum = 0;

	for (int i = 1; i <= N; i++) {
		cin >> a >> b;
		sum += a * b;
	}
	if (sum == X) {
		cout << "Yes";
	}
	else {
		cout << "No";
	}
	return 0;
}
