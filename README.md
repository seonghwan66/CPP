# kimseonghwan

#include <iostream>
#include <string>

using namespace std;

int main() {
    string str1 = "Hello";
    string str2 = "World";
    string str3;

    // 문자열 덧셈
    str3 = str1 + str2;
    cout << "str1 + str2 : " << str3 << endl;

    // 문자열 복사
    str3 = str1;
    cout << "str3 : " << str3 << endl;

    // 문자열 길이
    int len = str3.length();
    cout << "str3 length : " << len << endl;

    // 문자열 검색
    int idx = str3.find("lo");
    if (idx != string::npos) {
        cout << "lo found at index : " << idx << endl;
    }

    // 문자열 대체
    str3.replace(2, 2, "ai");
    cout << "str3 after replace : " << str3 << endl;

    return 0;
}
