# kimseonghwan

#include <iostream>
using namespace std;

int main() {
	int T, a, b;
	cin >> T;
	int c[100];

	for (int i = 0; i < T; i++) {
		cin >> a >> b;
		c[i] = a + b;
	}
	for (int i = 0; i < T; i++) {
		cout << c[i] << endl;
	}
	return 0;
}
