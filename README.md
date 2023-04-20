# kimseonghwan

#include <iostream>
using namespace std;

int main() {
	int n;
	cout<< "입력할정수의개수: ";
	cin>> n;
	if (n <= 0) {
		cout<< "양수를입력하세요.";
		
		return 0;
	}
	int* p = new int[n];    // 메모리할당
	if (!p) {     // if (p==NULL) 과같은의미
		cout<< "메모리를할당할수없습니다.";
		
		return 0;
	}
	cout<< n <<"개의정수를입력하세요. \n";
	for (int i= 0; i< n; i++)  cin>> p[i]; 
	cout<< "거꾸로하면다음과같습니다. \n";
	for (int i= n -1; i>= 0; i--)  cout<< p[i] << ' ';
	cout<< endl;
	delete[] p; // 메모리반환
}
