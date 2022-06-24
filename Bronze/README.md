### Bronze Problem Solving with logic :-

1. http://usaco.org/index.php?page=viewproblem2&cpid=1011
   Code :

```c++


#include<bits/stdc++.h>
using namespace std;
#define ll long long int
const ll mod=1000000007;
const double PI = 3.14159265358979323846;
#define FAST ios_base::sync_with_stdio(false); cin.tie(NULL); cout.tie(NULL)
#define fo(i ,n) for(ll i = 0 ; i < n ; i++)
#define mp make_pair
#define all(x) x.begin() , x.end()
#define ff first
#define ss second
#define pb push_back
#ifndef ONLINE_JUDGE
  #include "debug.h"
#else
#define deb(...)
#endif
void solve() {
	int n;
	cin >> n;
	vector <pair<int,int>> v(n);
	map <int,vector <int> > y;
	map <int,vector <int> > x;
	fo(i,n){
		cin >> v[i].ff >> v[i].ss;
		x[v[i].ff].pb(v[i].ss);
		y[v[i].ss].pb(v[i].ff);
	}
	for(auto j:x){
		sort(all(j.ss),greater<int>());
	}
	for(auto j:y){
		sort(all(j.ss),greater<int>());
	}
	int maxy=0;
	for(int i=0;i<n;i++){
		if(x[v[i].ff].size()>0 && y[v[i].ss].size()>0){
			int base=abs(v[i].ff-x[v[i].ff][0]);
			int height=abs(v[i].ss-y[v[i].ss][0]);
			maxy=max(maxy,base*height);
		}
	}
	cout << maxy << endl;
}
int32_t main(){
	// if (fopen("triangles.in", "r")) {
	// 	freopen("triangles.in", "r", stdin);
	// 	freopen("triangles.out", "w", stdout);
	// }
  	FAST;
  	int t=1;
	//cin >> t;
 	while(t--){
 		solve();
 	}
  	return 0;
}

```
