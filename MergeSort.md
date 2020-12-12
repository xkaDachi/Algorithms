```java
//mergeSort()
public static void mergeSort(int[] a, int n) {
    if (n < 2) {
        return;
    }
    int mid = n / 2;
    int[] leftArray = new int[mid];
    int[] rightArray = new int[n - mid];

    for (int i = 0; i < mid; i++) {
        leftArray[i] = a[i];
    }
    for (int i = mid; i < n; i++) {
        rightArray[i - mid] = a[i];
    }
    mergeSort(leftArray, mid);
    mergeSort(rightArray, n - mid);

    merge(a, leftArray, rightArray, mid, n - mid);
}

//merge()
public static void merge(int[] a, int[] leftArray, int[] rightArray, int left, int right) {
 
    int i = 0, j = 0, k = 0;
    
    while (i < left && j < right) {
        if (leftArray[i] <= rightArray[j]) {
            a[k++] = leftArray[i++];
        } else {
            a[k++] = rightArray[j++];
        }
    }
    while (i < left) {
        a[k++] = leftArray[i++];
    }
    while (j < right) {
        a[k++] = rightArray[j++];
    }
}
```
