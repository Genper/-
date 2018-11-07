# 此文档是用来记录一些简单的c++问题
1.#include<iostream>
#include<string>
using namespace std;
 
int main()
{
	string s;
	cin >> s;
	for (int i = 0; i < s.size(); i++)
	{
		if ((i + 1) == s.size())
			break;
		if (s[i] == s[i + 1])
		{
			s.erase(s.begin()+i);
			i--;
		}
	}
	cout << s << endl;
}
------------------------------------------------------



2.
#include<iostream>  
#include<string>  
#include<vector>  
using namespace std;  
int main()  
{  
    vector<char> chvec1,chvec2;  
    string str;  
    while (cin >> str)  
    {  
        for (int i = 0; i < str.size(); ++i)  
        {  
            chvec1.push_back(str[i]);  
            chvec2.push_back(str[i]);  
        }  
    }  
  
    char str1;  
  
    for (vector<char>::iterator iter = chvec1.begin(); iter != chvec1.end(); ++iter)  
    {  
        str1 = *iter;  
        int n = 0;  
        for (vector<char>::iterator iter1 = chvec2.begin(); iter1 != chvec2.end(); ++iter1)  
        {  
          
            if (str1 == *iter1)  
            {  
                n++;  
                if (n > 1)  
                {  
                    iter1 = chvec2.erase(iter1);  
                    --iter1;  
                }  
            }  
        }  
    }  
  
  
    for (vector<char>::iterator iter = chvec2.begin(); iter != chvec2.end(); ++iter)  
    {  
        cout << *iter;  
    }  
}  
      
--------------------- -------------------------------------------------------------


3.
#include <iostream>  
#include <algorithm>  
#include <string>  
#include <vector>  
using namespace std;  
int main()  
{  
    vector<char>chVec;  
    string str1;  
    while (cin >> str1)  
    {  
        if (str1.size() >= 1)  
        {  
            chVec.push_back(str1[0]);  
            for (int i = 1; i < str1.size(); i++)  
            {  
                int icount = count(chVec.begin(), chVec.end(), str1[i]);  
                if (icount == 0)  
                {  
                    chVec.push_back(str1[i]);  
                }  
            }  
        }  
      
        for (vector<char>::iterator iter = chVec.begin(); iter != chVec.end(); ++iter)  
        {  
            cout << *iter;  
        }  
        cout << endl;  
        chVec.clear();  
    }  
    return 0;  
}  
--------------------- ------------------------------------------------------
4.

#include<iostream>  
#include<string>  
#include<algorithm>  
#include<vector>  
using namespace std;  
int main()  
{  
    vector<char> chvec;  
    string str;  
    while (cin >> str)  
    {  
        for (int i = 0; i < str.size();++i)  
            chvec.push_back(str[i]);  
    }  
          
    reverse(chvec.begin(), chvec.end());  
    for (vector<char>::iterator iter = chvec.begin(); iter != chvec.end(); ++iter)  
    {  
        int icount = count(chvec.begin(), chvec.end(), *iter);  
        if (icount > 1)  
        {  
            iter = chvec.erase(iter);  
            if (iter != chvec.begin())  
                --iter;  
        }  
    }  
  
    reverse(chvec.begin(), chvec.end());  
    for (vector<char>::iterator iter = chvec.begin(); iter != chvec.end(); ++iter)  
    {  
        cout << *iter;  
    }  
}  
------------------------------------------------
