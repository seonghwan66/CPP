# kimseonghwan

#include <iostream>
using namespace std;

class ConvertSecond {
private:
	int hour, min, sec;
public:
	ConvertSecond();
	void setData();
	int getResult();
};
ConvertSecond::ConvertSecond() {
	hour = 0;
	min = 0;
	sec = 0;
}
void ConvertSecond::setData() {
	cout << "시(hour) 입력 : ";
	cin >> hour;
	cout << "분(minute) 입력 : ";
	cin >> min;
	cout << "초(second) 입력 : ";
	cin >> sec;
}
int ConvertSecond::getResult() {
	return (hour * 60 * 60) + (min * 60) + sec;
}
int main() {
	ConvertSecond a;
	a.setData();
	cout << "입력하신 시간은 총 " << a.getResult() << "초입니다." << endl;

	ConvertSecond b;
	cout << "기본 시간은 총 " << b.getResult() << "초입니다." << endl;
}
