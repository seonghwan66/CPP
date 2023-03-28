# kimseonghwan

#include <iostream>
using namespace std;

class Circle {
private:
	int radius;
public:
	Circle();
	Circle(int r);
	double getArea();
};
inline Circle::Circle() {
	radius = 1;
}
inline double Circle::getArea() {
	return 3.14 * radius * radius;
}
