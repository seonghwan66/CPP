# kimseonghwan

#include <iostream>
#include <cmath>
using namespace std;

class Line {
public:
	int sx, sy;
	int ex, ey;
	void setTwoPoints();
	double getLineLength();
};
void Line::setTwoPoints() {
	cout << "시작점 좌표 정수 두 개를 입력하세요.";
	cin >> sx >> sy;
	cout << "끝점 좌표 정수 두 개를 입력하세요.";
	cin >> ex >> ey;
}
double Line::getLineLength() {
	return sqrt(pow(ex - sx, 2) + pow(ey - sy, 2));
}
int main() {
	Line myline;
	myline.setTwoPoints();
	cout << "myline의 길이는 " << myline.getLineLength() << " 입니다.";
}
