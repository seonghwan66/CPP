# kimseonghwan

#include <iostream>
#include <string>
using namespace std;

class Student {
public:
	int number;
	string name;
	double grade;
};
int main() {
	Student s = { 1853330, "고흐", 3.7 };
	Student* p = &s;
	cout << s.number << s.name << s.grade << endl;
	cout << p->number << p->name << p->grade << endl;
	cout << s.number << s.name << s.grade << endl;
	cout << p->number << p->name << p->grade << endl;
	cout << (*p).number << (*p).name << (*p).grade << endl;
	cout << (*p).number << (*p).name << (*p).grade << endl;
}
