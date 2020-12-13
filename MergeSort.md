```java
/*
Complexity:
As merge sort is a recursive algorithm, the time complexity can be expressed as the following recursive relation:
T(n) = 2T(n/2) + O(n)
2T(n/2) corresponds to the time required to sort the sub-arrays and O(n) time to merge the entire array.
When solved, the time complexity will come to O(nLogn).
This is true for the worst, average and best case since it will always divide the array into two and then merge.
The space complexity of the algorithm is O(n) as we're creating temporary arrays in every recursive call.
*/

//mergeSort()
public static void mergeSort(int[] a, int n) {
    
    //base case
    if (n < 2) {
        return;
    }
    
    int mid = n / 2;
    int[] leftArray = new int[mid];
    int[] rightArray = new int[n - mid];

    //left side array
    for (int i = 0; i < mid; i++) {
        leftArray[i] = a[i];
    }
    
    //right side array
    for (int i = mid; i < n; i++) {
        rightArray[i - mid] = a[i];
    }
    
    //mergeSort() again both sides until we get to base case
    mergeSort(leftArray, mid);
    mergeSort(rightArray, n - mid);

    //merge left and right array depending on sort
    merge(a, leftArray, rightArray, mid, n - mid);
}

//merge()
public static void merge(int[] a, int[] leftArray, int[] rightArray, int left, int right) {
 
    int i = 0, j = 0, k = 0;
    
    //compares whichever left or right side is smaller for index k in a
    while (i < left && j < right) {
        if (leftArray[i] <= rightArray[j]) {
            a[k++] = leftArray[i++];
        } else {
            a[k++] = rightArray[j++];
        }
    }
    
    //fills the rest
    while (i < left) {
        a[k++] = leftArray[i++];
    }
    
    //fills the rest
    while (j < right) {
        a[k++] = rightArray[j++];
    }
}
```
