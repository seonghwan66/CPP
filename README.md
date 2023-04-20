# kimseonghwan

#include <iostream>
#include <string>
using namespace std;

int main() {

	string kor[] = { "개", "고양이", "기린", "코끼리", "표범" };
	string eng[] = { "dog", "cat", "giraffe", "elephant", "leopard" };
	string ox;
	int score(0);
	cout << "영단어로 바꾸세요." << endl;

	for (int i = 0; i < 5; i++) {
		string a;

		cout << kor[i] << " : ";
		getline(cin, a);

		if (a == eng[i]) {
			score += 20;
			ox += "o";
		}
		else {
			ox += "x";
		}

	}
	cout << ox << " " << score << " 점" << endl;
}
