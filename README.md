
# include <iostream>
using namespace std; 
int main(){
  string str; 
  cin>>str; 
  int n, m,i,temp,a,b,v; 
  n=str.length();
  cin>>m; 
  a=0;
  b=0;
  for(i=0;i<n;i++){
    if(str[i]=='?'){
      a++;
    }
    else
    if(str[i]=='*'){
      b++;
    }
  }
  if(a==0 && b==0){
    if(n==m){
      cout<<str; 
    }
    else{
      cout<<"Impossible";
    }
  }
  else
  if(a>0 && b==0){
    if(m>=n){
      cout<<"Impossible";
    }
    else{
    if(n-a==m){
      for(i=0;i<n;i++){
        if(str[i]!='?'){
          cout<<str[i];
        }
      }
    }
    
    else
    if((n-2*a)<=m && (n-a)>m){
      m=(n-a-m);
      for(i=0;i<n;i++){
        if(str[i+1]=='?' && (m!=0 && i!=n-1)){
          m--; 
        }
        else
        if(str[i]!='?'){
          cout<<str[i];
        }
      }
    }
    else
   {
      cout<<"Impossible";
    }
  }
  }
  else
  if(a==0 && b>0){
    if(n-2*b>m){
      cout<<"Impossible";
    }
      else{
    if(n-b==m){
      for(i=0;i<n;i++){
        if(str[i]!='*'){
          cout<<str[i];
        }
      }
    }
   else
    if(n-b>m && (n-2*b)<=m){
      m=(n-b-m);
      for(i=0;i<n;i++){
        if(str[i+1]=='*' && (m!=0 && i!=n-1)){
          m--;
        }
        else
        if(str[i]!='*'){
          cout<<str[i];
        }
      }
    } 
    else{
      v=0;
      for(i=0;i<n;i++){
        if(str[i+1]=='*' && (v==0 && i!=n-1)){
          temp=(m-n+b+1);
          while(temp--){
            cout<<str[i];
          }
          v=1;
        }
        else
        if(str[i]!='*' && str[i]!='?'){
          cout<<str[i];
        }
      }
    }
    }
    
  }
  else{
    temp=n-a-b; 
    if(temp>m){
      temp=temp-m; 
        for(i=0;i<n;i++){
   if((str[i+1]=='*' || str[i+1]=='?') && ((temp)!=0 && i!=n-1)){

     temp--; 
   }
   else
   if(str[i]!='*' && str[i]!='?'){
     cout<<str[i];
   }
        }
    }
    else{
      v=0;
      temp=(m-temp+1);
      for(i=0;i<n;i++){
        if(str[i+1]=='*' && (v==0 && i!=n-1)){
          while(temp--){
            cout<<str[i];
          }
          v=1;
        }
        else
        if(str[i]!='*' && str[i]!='?'){
          cout<<str[i];
        }
      }
    }
  }
  return 0;
}
