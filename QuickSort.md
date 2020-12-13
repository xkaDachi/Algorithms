```java
/*
Time Complexity
In the best case, the algorithm will divide the list into two equal size sub-lists. So, the first iteration of the full n-sized list needs O(n). 
Sorting the remaining two sub-lists with n/2 elements takes 2*O(n/2) each. As a result, the QuickSort algorithm has the complexity of O(n log n).
In the worst case, the algorithm will select only one element in each iteration, so O(n) + O(n-1) + … + O(1), which is equal to O(n2).
On the average QuickSort has O(n log n) complexity, making it suitable for big data volumes.
*/

public static void quickSort(int arr[], int begin, int end) {
	    if (begin < end) {
	    
	    	//get partition index
	        int partitionIndex = partition(arr, begin, end);
		
		//recursively call the same fct left and ride side of pivot/partition
	        quickSort(arr, begin, partitionIndex-1);
	        quickSort(arr, partitionIndex+1, end);
	    }
	}

//we compare the index of j and the index of pivot (last element)
//if element at index j < element at index pivot; increment i and swap i and j
//do that until we reach j == pivot; then pivot will be at index i + 1
private static int partition(int arr[], int begin, int end) {
	int pivot = arr[end];
	int i = (begin-1);

	//swap if element is smaller than pivot, increment i (swap index i and index j)
	//if element is larger than pivot, we do nothing
	for (int j = begin; j < end; j++) {
	        if (arr[j] <= pivot) {
	            i++;
	            int swapTemp = arr[i];
	            arr[i] = arr[j];
	            arr[j] = swapTemp;
	        }
	}
	
	//swap for to get proper index of pivot/partition
	int swapTemp = arr[i+1];
	arr[i+1] = arr[end];
	arr[end] = swapTemp;

	//index of the pivote/partition
	return i+1;
}
```
