# kimseonghwan

#include <iostream>
#include <string>
using namespace std;

int main() {
	string s = "Apple apple Boy boy Car car 끝";

	cout << "원래 문자열" << endl;
	cout << s << endl;

	cout << s.find('e') << endl;
	cout << s.find('e', 10) << endl;

	cout << s.substr(3, 5) << endl;
	cout << s.substr(10) << endl;
	cout << s.substr(10, 5) << endl;

	int f = s.find("apple");
	cout << f << endl;
	s.replace(f, 2, "맛있는 사과");

	cout << "바뀐 문자열 --> ";
	cout << s << endl;
}
