# kimseonghwan

#include <iostream>
using namespace std;

int main() {
	int a, b;
	cin >> a >> b;
	int max = (a < b) ? b : a;
	cout << "Max : " << max << endl;

	return 0;
}
