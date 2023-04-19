# kimseonghwan

#include <iostream>
using namespace std;

void print_array(int arr[][5]) {    //  (*arr)[5] 과동일
	for (int i = 0; i < 3; i++) {
		for (int j = 0; j < 5; j++)		cout << arr[i][j] << ' ';
		cout << endl;
	}
		cout << endl;
}
int main() {
	int a[3][5] = { 7 };	print_array(a);
	int b[3][5];	fill(b[0], b[3], 7);	print_array(b);
	int c[3][5];	fill_n(c[0], 15, 7);	print_array(c);
	
	return 0;
}
