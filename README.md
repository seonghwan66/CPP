# kimseonghwan

#include <iostream>
#include <string>
using namespace std;

int main() {
	string s;
	
	cout<< "여러줄 문자열을 입력하세요. 마지막에 & 입력 후 엔터키를 누르세요.\n";
	getline(cin, s, '&');
	cin.ignore();
	
	string f, r;
	cout<< "find: ";
	getline(cin, f);
	cout<< "replace: ";
	getline(cin, r);
	int sindex= 0;
	
	while (true) {
		int findex= s.find(f, sindex); // sindex부터문자열f 검색
		
		if (findex== -1)break;
		s.replace(findex, f.length(), r); // findex부터문자열f의길이만큼문자열r로변경
		
		sindex= findex+ r.length();
	}
	cout<< s << endl;
}
