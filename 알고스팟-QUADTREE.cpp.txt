#include<iostream>
#include<math.h>
#include<algorithm>
#include<utility>
#include<queue>
#include<vector>
#include<stdio.h>
#include<string>
using namespace std;
string quard(string::iterator &it)
{
	char c = *it;
	++it;
	if (c == 'w' || c == 'b')
	{
		return string(1, c);
	}

	string s1 = quard(it);
	string s2 = quard(it);
	string s3 = quard(it);
	string s4 = quard(it);

	return string("x") + s3 + s4 + s1 + s2;
}

int main()
{
	int testcase;
	cin >> testcase;
	while (testcase != 0)
	{
		string str;

		cin >> str;

		string::iterator it = str.begin();

		string result = quard(it);

		cout << result << endl;

		testcase--;
	}
	

	return 0;
}

