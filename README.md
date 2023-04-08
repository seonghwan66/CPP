# kimseonghwan

#include <iostream>
using namespace std;


int main() {

	int a[9];
	
	for (int i = 0; i < 9; i++) {
		cin >> a[i];
	}
	int x = -1;
	int y;

	for (int i = 0; i < 9; i++) {
		if (a[i] > x) {
			x = a[i];
			y = i;
		}
	}

	cout << x << endl << y+1 << endl;

	return 0;
}
