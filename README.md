#include <iostream>
using namespace std;

//Last occurence of a char
void lastOccLTR(string&str, char&ch , int index , int&ans){
  //base case
   if(index >= str.size()){
     return;
   }

   //ek case solve
   if(str[index] == ch){
     ans = index;
   }

   //RE
   lastOccLTR(str,ch,index+1,ans);
 }


void lastOccRTL(string&str, char&ch , int index , int&ans){
  //base case
  if(index < 0){
    return;
  }

  //ek case solve
  if(str[index] == ch){
    ans = index;
    return;
  }

  //RE
    lastOccRTL(str,ch,index-1,ans);
}

int main() {
  string str;
  cout<<"Enter your string: " ;
  cin>>str;
  char ch;
  cout<<"Enter character whose last occ is to be found: " ;
  cin>> ch;
  int ans = -1;
  lastOccRTL(str, ch , str.size()-1 , ans);
  cout << "Last occurence is: " << ans << endl;

  lastOccLTR(str, ch , 0 , ans);
  cout << "Last occurenceLTR is: " << ans << endl;

  return 0;
}
