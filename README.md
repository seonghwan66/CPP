# kimseonghwan

#include <iostream>
#include <string>
using namespace std;

int main() {
	string names[5];  // string 배열
	cout<< "이름 5개를 입력하세요.\n";
	for (int i= 0; i< 5; i++) {
	cout<< i<< "번: ";
	getline(cin, names[i]);
	}
	string latter = names[0];
	for (int i= 1; i< 5; i++) {
	if (latter < names[i]) // string 비교
		latter = names[i]; // string 대입
	}
	cout<< "사전에서 가장 뒤에 나오는 이름은 " << endl;
	cout<< latter << "입니다." << endl;
	}
