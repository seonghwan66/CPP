# kimseonghwan

#include<iostream>
using namespace std;

int main() {
	int a, b, c, reward = 0;
	cin >> a >> b >> c;

	if (a == b && b == c) {
		reward = 10000 + a * 1000;
	}
	else if (a == b || a == c) {
		reward = 1000 + a * 100;
	}
}
