# kimseonghwan

#include <iostream>
#include <cmath>
using namespace std;

class Line {
public:
	int sx, sy;
	int ex, ey;
	void setTwoPoints() {
		cout << "시작점 좌표 정수 두 개를 입력하세요.\n";
		cin >> sx >> sy;
		cout << "끝점 좌표 정수 두 개를 입력하세요.\n";
		cin >> ex >> ey;
	}
	double getLineLength() {
		return sqrt(pow(ex - sx, 2) + pow(ey - sy, 2));
	}
};			//선언부와 구현부 분리 없이 코딩
int main() {
	Line myline;
	myline.setTwoPoints();
	cout << "myline의 길이는 " << myline.getLineLength() << " 입니다.";
}
