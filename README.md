# cpp-progrm
//compression string 
#include<iostream>
#include<vector>
using namespace std;
int compress(vector<char>&chars){
    int n= chars.size();

   int idx =0;
    for(int i=0; i<n; i++){
        char ch = chars[i];
        int count =0;
        while (i<n && chars[i]==ch)  //comparing to var 
        {
            count++; i++;
        }
        if(count==1){
            chars[idx++] = ch;
        }else{
            chars[idx++] =ch;
            string str= to_string(count);
            for(char dig: str){
                chars[idx++]=dig;  //assing value 
            }
        }
        i--;
    }
    chars.resize(idx);
    return idx;


}
int main(){
    vector<char> s = {'a','a','b','b','c','c','c'};

   cout<<compress(s)<<" ";

  return 0;
}
