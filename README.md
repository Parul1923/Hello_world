# include <iostream>
using namespace std; 
int main(){
  int n,i,p,j, b, k; 
  cin>>n; 
  int ar[n],arr[n];
  for(i=0;i<n;i++){
    cin>>ar[i];
  }
  p=0;
  j=0;
  i=0;
  b=n-1;
  while(i<=b){
    if(ar[i]==-1){
      i++;
    }
    if(ar[b]==-1){
      b--;
    }
      if(ar[i]>p && ar[b]>p){
        if(ar[i]<ar[b]){
         k=i;
        arr[j]=0;
        i++;
        j++;
        }
        else{
          k=b;
          arr[j]=1;
          b--;
          j++;
        }
      }
      else
      if(ar[i]>p && ar[b]<p){
        k=i;
        arr[j]=0;
        i++;
        j++;
      }
      else
      if(ar[b]>p && ar[i]<p){
        k=b;
        arr[j]=1;
        b--;
        j++;
      }
      else{
        break; 
      }
      p=ar[k];
      ar[k]=-1;
  }
  if(ar[i]>p){
    arr[j]=0;
    j++;
  }
  cout<<j; 
  cout<<"\n";
  for(i=0;i<j;i++){
    if(arr[i]==0){
      cout<<"L";
    }
    else
    if(arr[i]==1){
      cout<<"R";
    }
  }
  return 0;
}
