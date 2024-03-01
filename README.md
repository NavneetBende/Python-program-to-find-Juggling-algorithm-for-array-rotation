 Juggling algorithm for array rotation
Here in this program we’ll be learning about Java program to find Juggling algorithm for array rotation. Juggling algorithm is one of the efficient algorithms used for array rotation. Now, let’s discuss about juggling algorithm and a program to rotate an array using the juggling algorithm.

Java program to find Juggling algorithm for array rotation
Keypoint
In this section we will learn about basic knowledge which we need to know before coding the above Program. So we must have knowledge of what is an array? 

What is an array?
An array is a data structure, it is collection of similar data elements which is stored at contiguous memory locations in which each data element can be accessed directly by only using its index number.
 
How to declare an array?
To declare an array in C,a programmer specifies the type of the elements and the number of elements required by an array as follows − This is called a single-dimensional array. The arraySize must be an integer constant greater than zero and type can be any valid C data type. For example, to declare a 10-element array called balanceof type double, use this statement − Here balanceis a variable array which is sufficient to hold up to 10 double numbers.
Algorithm
    Step 1- In this method, divide the array into M sets, where M = GCD (n, k), and then rotate the elements in each set.

    Step 2-From the number of elements ( n ) of the array and number of rotations ( k ) to be made to the array, the GCD(n, k) number of blocks are made.

    Step 3- Then in each block, shifting will take place to the corresponding elements in the block.

    Step 4- After all the elements in all the blocks are shifted, the array will be rotated for the given number of times.

    Step 5- For Example: If we want to rotate the below array by 2 positions.

  10 20 30 40 50 60

      M = GCD(6, 2) = 2;
      Initial Array : 10  20 30  40  50  60  
      First Set Moves : 50 20   10 40   30 60
      Second Set Moves : 50   60   10   20 30   40     
 
Juggling algorithm for array rotation java
Juggling Algorithm (Array Rotation In Place) Java
Java program to find Juggling algorithm for array rotation
public class PrepInsta
{
       public static int hcf(int a, int c) 
    { 
        if (c == 0) 
             return a; 
        else
             return hcf(c, a % b); 
    }
     //Function to left rotate array of by d number of rotations
    public static void leftRotate(int arr[], int d, int n) 
    { 
        int i, l, m, temp; 
        for (i = 0; i < hcf(d, n); i++)  // hcf(d,n) times the loop will iterate 
        { 
             // move i-th values of blocks 
            temp = arr[i]; 
            l = i; 
            while (true) { 
                m = l + d; 
                if (m >= n)  // The element has to be shifted to its rotated position
                    m = m - n; 
                if (m == i)  // The element is already in its rotated position
                    break; 
                arr[l] = arr[m]; 
                l = m; 
            } 
            arr[l] = temp; 
        }} 
     //  Main function
    public static void main(String[] args) 
    { 
        int arr[] = { 10, 20 30, 40, 50, 60, 70 }; 
        int no_of_rotation = 3;
        int n = arr.length;
        System.out.println( "Array Elements before rotating : "); 
        for(int i = 0 ; i < n ; i++)
        {
            System.out.print(arr[i]+  " "); 
        }
        leftRotate(arr, no_of_rotations, n); 
        System.out.println( "Array Elements after rotating : "); 
        for(int i = 0 ; i < n ; i++)
        {
            System.out.print(arr[i] +  " ");   }
 }
 }
Output:-
input elements of array
{10,20,30,40,50,60,70}

output after juggling
60,70,10,20,30,40,50
