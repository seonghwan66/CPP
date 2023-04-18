# kimseonghwan

// 04.21 다시보기

#include <iostream>
#include <cstring>
using namespace std;

int main()
{
    char a[100] = "안녕하세요?!";
    char b[100] = "날씨가 참 좋군요ㅎㅎㅎ";
    char c[100] = "안녕히 계세요!!!";
    
    cout << "함수 사용" << endl;
    cout << strlen(a) << " " << strlen(b) << " " << strlen(c) << endl;
    

    int i, j, l=0;
    while(true){
        if(a[i]==NULL)
        {
            break;
        }
        else
            i++;
    }
    while(true){
        if(b[j]==NULL)
        {
            break;
        }
        else
            j++;
    }
    while(true){
        if(c[l]==NULL)
        {
            break;
        }
        else
            l++;
    }
    cout << "반복문으로 계산" << endl;
    cout << i << " " << j << " " << l;
}
