Non Repeating Elements in an array in C++
Here, in this section we will discuss the program to print non repeating elements in an array in C++ programming language. We will discuss different methods to print the unique elements of the given input array.

Distinct element of an array in C++
While loop in C
Methods Discussed in this Page are :
Method 1 : Using Two loops
Method 2 : Using hash Map
Let’s discuss each method one by one,

Method 1 :
In this method we will count the frequency of each elements using two for loops and print those elements which occurs on;y one time in the given input array.

To check the status of visited elements create a array of size n.
Run a loop from index 0 to n and check if (visited[i]==1) then skip that element.
Otherwise create a variable count = 1 to keep the count of frequency.
Run a loop from index i+1 to n
Check if(arr[i]==arr[j]), then increment the count by 1 and set visited[j]=1.
After complete iteration of inner for loop check if(count==1), then print that ith element.
Time and Space Complexity :
Time Complexity : O(n2)
Space Complexity : O(n)
Related Pages
Counting Distinct Elements in an Array

Finding  Repeating elements in an Array

Removing Duplicate elements from an array

Finding Minimum scalar product of two vectors

Finding Maximum scalar product of two vectors in an array 

Method 1 : Code in C++
Run
#include <bits/stdc++.h>
using namespace std;

// Main function to run the program
int main() 
{ 
    int arr[] = {10, 30, 10, 20, 40, 20, 50, 10}; 
    int n = sizeof(arr)/sizeof(arr[0]); 

    int visited[n], count_dis=0;

    for(int i=0; i<n; i++){

        if(visited[i]!=1){
           int count = 1;
           for(int j=i+1; j<n; j++){
              if(arr[i]==arr[j]){
                 count++;
                 visited[j]=1;
              }
            }
            if(count==1)
             cout<<arr[i]<<" ";
         }
     }
 
    return 0; 
}
Output :
30 50 
Method 2 :
In this method we will use hash-map to store the frequency of the elements and print those elements which have frequency equals to 1.

Create an unordered_map say mp.
Run a loop to iterate over array
Set mp[arr[i]]++
After, complete iteration, run a loop over map
Check if value == 1, then print the key.
Time and Space Complexity :
Time Complexity : O(n)
Space Complexity : O(n)
Non repeating elements in an array in C++
Method 2 : Code in C++
Run
#include <bits/stdc++.h>
using namespace std;

// Main function to run the program
int main() 
{ 
   int arr[] = {10, 30, 40, 20, 10, 20, 50, 10}; 
   int n = sizeof(arr)/sizeof(arr[0]); 

   unordered_map <int, int>mp;
   int count_dis=0;

   for(int i=0; i<n; i++)
      mp[arr[i]]++;

   for(auto it=mp.begin(); it!=mp.end(); it++){
       if(it->second==1)
          cout<<it->first<<" ";
   }
 
}
Output :
50 40 30 
