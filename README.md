# kimseonghwan

#include <iostream>
#include <fstream>
using namespace std;

int main() {
	char source[] = "source.txt";
	ifstream fin(source);
	ofstream fout("copy.txt");

	if (!fin || !fout) {
		cout << source << " 열기오류";
		return 0;
	}
	
	int count = 0;
	int c;
	
	while ((c = fin.get()) != EOF) {
		cout << (char)c;
		fout << (char)c;
		count++;
	}
	
	cout << endl << endl;
	cout << "---------------------------" << endl;	
	cout << "읽은 바이트 수는" << count << endl;
	
	fin.close();
	fout.close();

	return 0;
}
