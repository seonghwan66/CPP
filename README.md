# kimseonghwan

#include <iostream>
using namespace std;

int main() {

	int A, B, C;
	cin >> A >> B >> C;

	
	int min = 60 * A + B;

	min += C;

	int hour = (min / 60) % 24;
	min = min % 60;

	cout << hour << " " << min;

	return 0;
}
