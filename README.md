# kimseonghwan

#include <iostream>
using namespace std;

int main() {
	int N, v;
	int a[100];
	int count = 0;
	cin >> N;
	for (int i = 0; i < N; i++) {
		cin >> a[i];
	}
	cin >> v;
	for (int j = 0; j < N; j++) {
		if (v == a[j]) {
			count += 1;
		}
		else {
			count += 0;
		}
	}
	cout << count;

	return 0;
}
