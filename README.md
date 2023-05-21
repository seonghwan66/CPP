# kimseonghwan

#include <iostream>
#include <fstream>
#include <string>

using namespace std;

int main() {
    ifstream fin("둘리.txt");
    ofstream fout("dooli.txt");

    if (!fin || !fout) {
        cerr << "파일 열기 실패" << endl;
        return 1;
    }

    string s;
    getline(fin, s, '&');
    string f, r;

    cout << "고치기 전 단어: ";
    getline(cin, f);

    cout << "고치기 후 단어: ";
    getline(cin, r);

    int sindex = 0;

    while (true) {
        int findex = s.find(f, sindex);
        if (findex == -1) break;

        s.replace(findex, f.length(), r);
        sindex = findex + r.length();
    }

    fout << s << endl;

    fin.close();
    fout.close();

    cout << "처리 완료. dooli.txt를 열어서 결과를 확인하세요." << endl;

    return 0;
}
