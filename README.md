# kimseonghwan

#include <iostream>
using namespace std;

void print_array(int* arr) {
	for (int i = 0; i < 5; i++)  cout << arr[i] << ' ';
	cout << endl;
}
int main() {
	int a[5]; print_array(a);
	int b[5] = {};	print_array(b);
	int c[5] = { 0, };	print_array(c);
	int d[5] = { 7, };  print_array(d);

	int e[5]; fill(e, e + 5, 7); print_array(e);
	int f[5]; fill_n(f, 5, 7); print_array(f);

	return 0;
}
