# kimseonghwan

#include <iostream>
using namespace std;

class ThreeMatrices {
	int a[2][5] = { {5, 10, 2, 7, 5}, { 4, 6, 2, 2, 9} };
	int b[2][5] = { {5, 2, 7, 4, 5}, { 10, 6, 9, 2, 3} };
	int c[2][5];
public:
	ThreeMatrices();
	void buildC(char op);
	void printC();
};
ThreeMatrices::ThreeMatrices() {
	fill_n(c[0], 10, 0);
}
void ThreeMatrices::buildC(char op) {
	for (int i = 0; i < 2; i++) {
		for (int j = 0; j < 5; j++) {
			if (op == '+')
				c[i][j] = a[i][j] + b[i][j];
			else
				c[i][j] = a[i][j] - b[i][j];
		}
	}
}
void ThreeMatrices::printC() {
	for (int i = 0; i < 10; i++) {
			cout << c[i/5][i%5] << " ";
			if (i%5 == 4) {
				cout << endl;
			}
	}
}
int main() {
	ThreeMatrices m;
	cout << "Add..." << endl;
	m.buildC('+');
	m.printC();
	cout << "Subtract..." << endl;
	m.buildC('-');
	m.printC();
}
