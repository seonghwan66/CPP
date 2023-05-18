# kimseonghwan

#include<iostream>
#include<fstream>
#include<string>
using namespace std;

int main() {
	ifstream apple1("a1.txt");
	ifstream apple2("a2.txt");
	ifstream apple3("a3.txt");
	ofstream cloud("b.txt", ios::app);

	if (!apple1 || !apple2 || !apple3 || !cloud) {
		cerr << "파일 열기 실패" << endl;
		return 1;
	}

	string line;
	while (getline(apple1, line)) {
		cloud << line << endl;
	}
	apple1.close();

	while (getline(apple2, line)) {
		cloud << line << endl;
	}
	apple2.close();

	while (getline(apple3, line)) {
		cloud << line << endl;
	}
	apple3.close();

	cloud.close();

	cout << "파일 합치기 완료" << endl;

	return 0;
}
