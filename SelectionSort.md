```java
/*
selecting the smallest element required a total of (n-1) comparisons followed by swapping it to the 1st position. 
Similarly, selecting the next smallest element required total (n-2) comparisons followed by swapping in the 2nd position, and so on.
The formula for the sum of n natural numbers is n(n+1)/2.
As n^2 grows prominently as n grows, we consider the higher power of n as the performance benchmark, making this algorithm have a time complexity of O(n^2).

In terms of auxiliary space complexity, Selection Sort requires one extra variable to hold the value temporarily for swapping. 
Therefore, Selection Sort's space complexity is O(1).
*/

public static void sortAscending(final int[] arr) {
    for (int i = 0; i < arr.length - 1; i++) {
        int minElementIndex = i;
        for (int j = i + 1; j < arr.length; j++) {
            if (arr[minElementIndex] > arr[j]) {
                minElementIndex = j;
            }
        }

        if (minElementIndex != i) {
            int temp = arr[i];
            arr[i] = arr[minElementIndex];
            arr[minElementIndex] = temp;
        }
    }
}
```
