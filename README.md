# kimseonghwan

#include <iostream>
using namespace std;

class ThreeMatrices {
    int a[2][5] = { {5, 10, 2, 7, 5}, {4, 6, 2, 2, 9} };
    int b[2][5] = { {5, 2, 7, 4, 5}, {10, 6, 9, 2, 3} };
    int c[2][5];
public:
    void buildC(char op);
    void printC();
};
void ThreeMatrices::buildC(char op) {
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 5; j++) {
            if (op == '+')
                c[i][j] = a[i][j] + b[i][j];
            else if (op == '-')
                c[i][j] = a[i][j] - b[i][j];
        }
    }
}
void ThreeMatrices::printC() {
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 5; j++) {
            cout << c[i][j] << " ";
        }
        cout << endl;
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
