# kimseonghwan

#include <iostream>
#include <fstream>
#define N 10
using namespace std;

int main() {
	int a[N];
	ifstream fa("a.txt");
	ofstream fb("b.txt");

	if (!fa || !fb) {
		cerr << "파일 열기 실패" << endl;
		return 1;
	}
	for (int i = 0; i < N; i++) {
		fa >> a[i];
	}
	for (int i = N-1; i >= 0; i--) 
		fb << a[i] << endl;
	
	fa.close();
	fb.close();

	cout << "처리완료. b.txt를 열어서 결과를 확인하세요." << endl;

	return 0;
}
