# Stacks001
#include<bits/stdc++.h>
using namespace std;
bool checkexpression(string s)
{
	stack <char> s1;
	for(int i=0;i<s.size();i++)
	{ 
		if(s[i]==')')
		{
			char up=s1.top();
			s1.pop();

			int insideelement=0;
			while(up!='(')
			{
				insideelement++;
				up=s1.top();
				s1.pop();
			}
			if(insideelement<1)
			return 1;
	    }
		else
		s1.push(s[i]);
     }
	 return false;
}
int main() {
	int t;
	cin>>t;
	while(t--)
	{
		string s;
		cin>>s;
		if(checkexpression(s))
		cout<<"Duplicate"<<endl;
		else
		cout<<"Not Duplicates"<<endl;
	}
	return 0;
}
