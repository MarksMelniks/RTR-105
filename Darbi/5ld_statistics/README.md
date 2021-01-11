    // C program for implementation of Bubble sort 
    #include <stdio.h> 
  
    void swap(int *xp, int *yp) 
    { 
    int temp = *xp; 
    *xp = *yp; 
    *yp = temp; 
    } 
  
    // A function to implement bubble sort 
    void bubbleSort(int arr[], int n) 
    { 
    int i,j; 
    for (i = 0; i < n-1; i++)       
  
       // Last i elements are already in place    
       for (j = 0; j < n-i-1; j++)  
           if (arr[j] > arr[j+1]) 
              swap(&arr[j], &arr[j+1]);
    } 

    /* Function to print an array */
    void printArray(int arr[], int size) 
    { 
    int i; 
    for (i=0; i < size; i++) 
        printf("%c ", arr[i]); 
    printf("\n"); 
    } 

    // Driver program to test above functions 
    int main() 
    { 
    int arr[] = {'q', 's', 'j', 'e', 'x', 'b', 'h', 'y', 'u', 'f', 'g', 'm'};
   
    
    int n = sizeof(arr)/sizeof(arr[0]);
    bubbleSort(arr, n);
    char max=sizeof(arr)/sizeof(arr[0]) - 1;
    
    printf("Sorted array: \n"); 
    printArray(arr, n);
    
    
   
    printf("min %c\n",arr[0]);
    printf("max %c\n",arr[max]);
    
    return 0; 
    } 
