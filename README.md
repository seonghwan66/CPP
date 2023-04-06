# kimseonghwan

#include <iostream>
using namespace std;

int main() {
	int n;
	cin >> n;
	
	int a[n + 1];
	int min = 1000000;
	int max = -1000000;

	for (int i = 0; i < n; i++) {
		cin >> a[i];

		if (min > a[i]) {
			min = a[i];
		}
		if (max < a[i]) {
			max = a[i];
		}
	}

	cout << min << " " << max << endl;

	return 0;
}
