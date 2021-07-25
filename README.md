# array
///////////
REVERSE ARRAY 

#include <iostream>
#include<algorithm>
#include<set>
#include<bits/stdc++.h> 
using namespace std;
void reverse(int arr[] , int n){
    
    int low=0;
    int high = n-1;
    while(low<=high){
        swap(arr[low],arr[high]);
        low++;
        high--;
    }
    
    
}

void print(int arr[] , int n){
    for(int i=0;i<n;i++){
        cout<<arr[i];
    }
}
int main() {
    int n;
    cin>>n;
    int arr[n];
    for(int i=0;i<n;i++){
        cin>>arr[i];
    }
 reverse(arr,n);
  print(arr,n);
	return 0;
  
  
  ////////////////////////////////
  MAX MIN 
  
  
  
  #include <iostream>
#include<algorithm>
#include<set>
#include<bits/stdc++.h> 
using namespace std;
void reverse(int arr[] , int n){
    int maxi = INT_MIN;
    int mini = INT_MAX;
for(int i=0;i<n;i++){
    maxi = max(maxi,arr[i]);
    mini = min(mini,arr[i]);
}
    cout<<maxi;
    cout<<mini;
   
    
}


int main() {
    int n;
    cin>>n;
    int arr[n];
    for(int i=0;i<n;i++){
        cin>>arr[i];
    }
 reverse(arr,n);

	return 0;
}
/////////////////////////////////////////////
  
  
  sort 0s 1s 2s
  
  
  #include <iostream>
#include<algorithm>
#include<set>
#include<bits/stdc++.h> 
using namespace std;
void countt(int arr[] , int n){
    int count0 = 0;
    int count1 = 1;
    int count2 = 2;
    for(int i=0;i<n;i++){
        if(arr[i] == 0){
            count0++;
        }
        if(arr[i] ==1){
            count1++;
        }
        if(arr[i] ==2){
            count2++;
        }
        
    }
        for(int i=0;i<count0;i++){
            arr[i] = 0;
        }
         for(int i=count0;i<count0+count1;i++){
            arr[i] = 1;
        }
         for(int i=count1+count0;i<n;i++){
            arr[i] = 2;
        }
        
        
    
}


int main() {
    int n;
    cin>>n;
    int arr[n];
    for(int i=0;i<n;i++){
        cin>>arr[i];
    }
countt(arr,n);
 for(int i=0;i<n;i++){
     cout<<arr[i];
 }

	return 0;
}
                  
                  
                  
 ////////////////////////
                  
                  MOVE ALTERNATE 
                  
                  
                  
                  #include <iostream>
#include<algorithm>
#include<set>
#include<bits/stdc++.h> 
using namespace std;
void alter(int arr[] , int n){
    int l =0;
    int h =n-1;
    
while(l<h){
    
    if(arr[l] > 0 && arr[h] < 0){
        swap(arr[l] ,arr[h]);
        l++;
        h--;
    }
    
    else if (arr[l] < 0){
        l++;
    }
    
    else if(arr[h] >0){
        h--;
    }
    }
}


int main() {
    int n;
    cin>>n;
    int arr[n];
    for(int i=0;i<n;i++){
        cin>>arr[i];
    }
alter(arr,n);
 for(int i=0;i<n;i++){
     cout<<arr[i]<<" ";
 }

	return 0;
}
       ////////////////////////////////
                    
                    
            UNION
                    #include <iostream>
#include<iterator>
#include<algorithm>
#include<bits/stdc++.h> 
using namespace std;
void getunion(int arr[] ,int n, int b[], int m){
     set<int>s;
    for(int i=0;i<n;i++){
        s.insert(arr[i]);
    }

    for(int i=0;i<m;i++){
        s.insert(b[i]);
    }
cout<<s.size()<<" ";
    
    for(auto itr = s.begin() ;itr !=s.end();itr++){
        cout<<*itr<<" ";
    }
 
}


int main() {
    int n,m;
    cin>>n>>m;
    int arr[n];
    int b[m];
    for(int i=0;i<n;i++){
        cin>>arr[i];
    }
    for(int i=0;i<n;i++){
        cin>>b[i];
    }
getunion(arr,n,b,m);

	return 0;
}
  /////////////////////////////////////////////
  INTERSECTION
  
  #include <iostream>
#include<iterator>
#include<algorithm>
#include<bits/stdc++.h> 
using namespace std;
void getunion(int arr[] ,int n, int b[], int m){
 int i=0;
 int j=0;
 
 while(i < n && j<m){
    if(arr[i] > b[j]){
        i++;
    }
    
    else if(b[j] > arr[i]){
        j++;
    }
    
    else{
        cout<<arr[i]<<" ";
        i++;
        j++;
        
    }
    
 }
 
}


int main() {
    int n,m;
    cin>>n>>m;
    int arr[n];
    int b[m];
    for(int i=0;i<n;i++){
        cin>>arr[i];
    }
    for(int i=0;i<n;i++){
        cin>>b[i];
    }
getunion(arr,n,b,m);

	return 0;
}
  ///////////////
  rotate by m
  #include <iostream>
#include<iterator>
#include<algorithm>
#include<bits/stdc++.h> 
using namespace std;
void reverse(int arr[] , int l ,int h){
    while(l<=h){
        swap(arr[l],arr[h]);
        l++;
        h--;
    }
}

void rotate(int arr[] , int n, int d){
 
 
 reverse(arr,0,d-1);
 reverse(arr,d,n-1);
 reverse(arr,0,n-1);
 
 
}



int main() {
    int n,m;
    cin>>n>>m;
    int arr[n];

    for(int i=0;i<n;i++){
        cin>>arr[i];
    }
  
rotate(arr,n,m);
for(int i=0;i<n;i++){
    cout<<arr[i];
}
	return 0;
}

                 ///////////////////////
                 MAXIMUM SUBARRAY SUM
                 
                 #include <iostream>
#include<iterator>
#include<algorithm>
#include<bits/stdc++.h> 
using namespace std;
int maxsum(int arr[] , int n){
          int sum =0;
          int maxi = INT_MIN;
    for(int i=0;i<n;i++){
   sum =sum+arr[i];
   maxi = max(maxi, sum);
   if(sum <0){
       sum =0;
   }
    }
    return sum;
}


int main() {
    int n;
    cin>>n;
    int arr[n];

    for(int i=0;i<n;i++){
        cin>>arr[i];
    }
  
cout<<maxsum(arr,n);
// 
	return 0;
}
