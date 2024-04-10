#include <bits/stdc++.h>
using namespace std;

int n, a[100], ok, cnt;

void ktao(){
	cnt=1; // so so hang dc tach
	a[1]=n; //phan tu dau tien
}
void sinh(){
	int i=cnt;
	while(i>=1 && a[i]==1 ) i--;
	if(i==0) ok=0;
	else{
		a[i]-=1;
		int d=cnt-i+1;  //phan con thieu
		cnt= i;
		int q=d/a[i];
		int r=d%a[i];
		if(q){
			while(q){
				a[++cnt]=a[i];
				q--;
			}
		}
		if(r){
			a[++cnt]=r;
		}
	}
}
void in(){
	for(int i=1 ; i<=cnt ; i++){
		cout<<a[i]<<" ";
	}
	cout<<endl;
}
int main(){
	cin>>n;
	ok=1;
	ktao();
	while(ok){
		in();
		sinh();	
	}
}
