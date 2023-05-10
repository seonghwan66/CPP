# kimseonghwan

#include <iostream>
#include <fstream>
#include <iomanip>
using namespace std;

int main() {
	int  temp, sum=0;
	ifstream fa("a.txt");
	ofstream fb("b.txt");

	if (!fa || !fb) {
		cerr << "파일 열기 실패" << endl;
		return 1;
	}

	for (int i = 0; i < 5; i++) {
		fa >> temp;
		sum += temp;
	}

	fb << "합계 : " << sum << endl;
	fb << "평균 : " << fixed << setprecision(1) << (double)sum / 5 << endl;
	fa.close();
	fb.close();

	cout << "처리 완료. b.txt를 열어서 결과를 확인하세요." << endl;

	return 0;
}
