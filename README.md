# Java-Program-for-Finding-the-Smallest-and-largest-element-in-an-array

Finding the Smallest and largest element in an array in Java
We have already given two different articles on how to find the smallest and how to find the largest element in an array, in this article we’ll teach you how to write a Java Program for Finding both the Smallest and largest element in an array in java programming language.

Java Program for Finding the Smallest and largest element in an array
Methods Discussed
Method 1 : Using Iteration
Method 2 : Using Recursion (Top-Down Approach)
Method 3 : Using Bottom-up recursive approach
Example :
Input :
arr[5] = [12, 56, 45, 34, 30]

Output :
Smallest Element is 12
Largest Element is 56
Method 1 :
In this method we will use loop to find maximum and minimum element of the given input array. You can check out the following pages to find the smallest and largest element of the array :

Smallest element in an array
Largest element in an array
largest and smallest element
Method 1 : Code in Java
Run
import java.util.Scanner;

public class Main
{
   public static void main(String args[])
   {

       int arr[] = {12, 13, 1, 10, 34, 10};

       int largest = arr[0], smallest=arr[0];

       for(int i=0; i<arr.length; i++) { if(smallest > arr[i])
              smallest = arr[i];
           if(largest < arr[i])
              largest = arr[i];

       }

       System.out.println(smallest);
       System.out.println(largest);
   }
}
Output
1

34
Related Pages
Find Largest element in an array
 
Find Smallest Element in an Array
 
Find Second Smallest Element in an Array

Calculate the sum of elements in an array 

Reverse an Array

Method 2 :
In this method we will use recursive approach (top-down ) to find maximum and minimum element of the given input array. You can check out the following pages to find the smallest and largest element of the array :

Smallest element in an array
Largest element in an array
Let's see How Recursive Calls were made to find the maximum element of the array.

Let's the input array is arr[5] = [45, 78, 90, 23, 10], n = 5
Initially we pass arr and 5 to getmax(arr, 5) function, then
getmax(arr, 5) return max(arr[4], getmax(arr, 4))
getmax(arr, 4) return max(arr[3], getmax(arr, 3))
getmax(arr, 3) return max(arr[2], getmax(arr, 2))
getmax(arr, 2) return max(arr[1], getmax(arr, 1))
getmax(arr, 1) return arr[0]
In this way recursive calls will help to find the maximum element among the 5 elements of the given input array.
Method 2 : Code in Java
Run

import java.util.Scanner;

public class Main
{
  static int getmin(int arr[], int n){
     if(n==1)
       return arr[0];

     return Math.min(arr[n-1], getmin(arr, n-1));
  }
  static int getmax(int arr[], int n){
     if(n==1)
      return arr[0];

     return Math.max(arr[n-1], getmax(arr, n-1));
  }
  public static void main(String args[])
  {

    int arr[] = {12, 13, 1, 10, 34, 10};
    int n = arr.length;
    System.out.println(getmin(arr, n));
    System.out.println(getmax(arr, n)); 
   }
}
Output
1

34
Method 3 :
In this method we will use recursive approach (bottom-up ) to find maximum and minimum element of the given input array. You can check out the following pages to find the smallest and largest element of the array :

Smallest element in an array
Largest element in an array
Method 3 : Code in Java
Run
import java.util.Scanner;

public class Main
{
   static int minimum(int arr[], int i, int end)
   {
     int min;

     if(i == end-1)
       return (arr[i] < arr[i + 1]) ? arr[i] : arr[i + 1];

     min = minimum(arr, i + 1, end);

     return (arr[i] < min) ? arr[i] : min; } static int maximum(int arr[], int i, int end) { int max; // when we reach 2nd last array element // return the larger b/w last & 2nd last elements 
if(i == end-1) return (arr[i] > arr[i + 1]) ? arr[i] : arr[i + 1];

      max = maximum(arr, i + 1, end);

      return (arr[i] > max) ? arr[i] : max;
   }
   public static void main(String args[])
   {

       int arr[] = {12, 13, 1, 10, 34, 10};
       int n = arr.length;
       System.out.println(minimum(arr, 0, n-1));
       System.out.println(maximum(arr, 0, n-1)); 
   }
}
Output
1

34
