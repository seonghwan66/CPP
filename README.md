# kimseonghwan

#include <iostream>
#include <fstream>
#include <algorithm>
using namespace std;

int main() {
	double arr[31];
	ifstream fin("sort_before.txt");
	ofstream fout("sort_after.txt");


	for (int i = 0; i < 31; i++) fin >> arr[i];
	sort(arr, arr+31, greater<double>());	//기본은 오름차순, 3번 째에 넣으면 내림차순, arr 배열 정렬해서 업데이트, greater<double>() 일단 외우기. 나중에 배움.

	for (int i = 0; i < 31; i++) fout << arr[i] << endl;




	fin.close(); fout.close();
	cout << "end\n";

	return 0;
}
