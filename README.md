# leetcode-twosum
#include <unordered_map>    
#include<iostream>
using namespace std;
class Solution{
public:
	vector<int>	twosum(vector<int>& num,int target){
	unordered_map<int,int> hash;
	vector<int>result;
	int numbertofind=0;
	for(int i=0;i<num.size();i++){
		numbertofind=target-num[i];
		if(hash.find(numbertofind)!=hash.end()){
		result.push_back(hash[numbertofind]);
		result.push_back(i+1);
		}
		else{
		hash[num[i]]=i+1;
		}
	}
	return result;
	}

};
void main(){
	int array[]={1,2,3,4,5};
	vector<int> num(array,array+sizeof(array)/sizeof(int));
	int target=0;
	cin>>target;
	Solution s;
	vector<int>result=s.twosum(num,target);
	for(vector<int>::iterator a=result.begin();a!=result.end();a++){
	cout<<*a;
	cout<<" "<<*++a;
	cout<<endl;
	}
}
