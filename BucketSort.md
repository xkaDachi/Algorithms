```java
/*
bucketSort(arr[], n)
1) Create n empty buckets (Or lists).
2) Do following for every array element arr[i].
.......a) Insert arr[i] into bucket[n*array[i]]
3) Sort individual buckets using insertion sort.
4) Concatenate all sorted buckets.

Time Complexity: If we assume that insertion in a bucket takes O(1) time then steps 1 and 2 of the above algorithm clearly take O(n) time. 
The O(1) is easily possible if we use a linked list to represent a bucket (In the following code, C++ vector is used for simplicity). 
Step 4 also takes O(n) time as there will be n items in all buckets. 
The main step to analyze is step 3. This step also takes O(n) time on average if all numbers are uniformly distributed (please refer CLRS book for more details)
Following is the implementation of the above algorithm.
*/

    // Function to sort arr[] of size n 
    // using bucket sort 
    static void bucketSort(float arr[], int n) { 
        if (n <= 0) 
            return; 
  
        // 1) Create n empty buckets 
        @SuppressWarnings("unchecked") 
        Vector<Float>[] buckets = new Vector[n]; 
  
        for (int i = 0; i < n; i++) { 
            buckets[i] = new Vector<Float>(); 
        } 
  
        // 2) Put array elements in different buckets 
        for (int i = 0; i < n; i++) { 
            float idx = arr[i] * n; 
            buckets[(int)idx].add(arr[i]); 
        } 
  
        // 3) Sort individual buckets 
        for (int i = 0; i < n; i++) { 
            Collections.sort(buckets[i]); 
        } 
  
        // 4) Concatenate all buckets into arr[] 
        int index = 0; 
        for (int i = 0; i < n; i++) { 
            for (int j = 0; j < buckets[i].size(); j++) { 
                arr[index++] = buckets[i].get(j); 
            } 
        } 
    }
```
