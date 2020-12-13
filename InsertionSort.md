```java
/*
The time taken by the Insertion Sort procedure to run is O(n^2). 
For each new item, we iterate from right to left over the already sorted portion of the array to find its correct position. 
Then we insert it by shifting the items one position to the right.
The algorithm sorts in place so its space complexity is O(1) for the imperative implementation and O(n) for the recursive implementation.
/*

public static void insertionSort(int[] input) {
	//keep track of index of i and j (i - 1)
	for (int i = 1; i < input.length; i++) { 
	
	    int key = input[i]; 
	    int j = i - 1;
	    
	    //work from index 0 up to index i/j to sort
	    while (j >= 0 && input[j] > key) {
	    	//sort
	        input[j + 1] = input[j];
	        j = j - 1;
		
	    }
	    //sort
	    input[j + 1] = key; 
	}
}
```
