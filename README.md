# kimseonghwan

#include <iostream>
using namespace std;

int main() {
	int T;
	cin >> T;

	int i = 1;
	while(i <= T) {
		int a;
		int b;
		cin >> a >> b;
		
		cout << "Case #" << i << ": " << a << " + " << b << " = " << a + b << endl;

		i++;
	}
	
	return 0;
}
