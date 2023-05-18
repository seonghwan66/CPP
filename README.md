# kimseonghwan

#include<iostream>
#include<fstream>
#include<iomanip>
#include<algorithm>
#include<string>
using namespace std;

int main() {

	ifstream fin("score.txt");
	ofstream fout("result.txt");

	if (!fin || !fout) {
		cerr << "파일 열기 실패" << endl;
		return 1;
	}

	string name;
	double score;
	double sum = 0;
	double max_score = 0;
	int count = 0;

	while (fin >> name >> score) {
		sum += score;
		max_score = max(max_score, score);
		count++;
	}

	double avg = sum / count;

	fout << fixed << setprecision(2) << "합계 : " << sum << endl;
	fout << fixed << setprecision(2) << "평균 : " << avg << endl;
	fout << fixed << setprecision(2) << "최고 점수 : " << max_score << endl;

	fin.close();
	fout.close();

	cout << "처리완료. result.txt를 열어서 결과를 확인하세요." << endl;

	return 0;
}
