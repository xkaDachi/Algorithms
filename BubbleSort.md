```java
/*
Te space complexity, even in the worst scenario, is O(1) as Bubble sort algorithm doesn't require any extra memory and the sorting takes place in the original array.
In case of a sorted array, swapping won't be needed in the first iteration itself – which means we can stop the execution. 
This is the best case scenario and the time complexity of the algorithm is O(n).
To summarize, it's an in-place stable algorithm, with time complexity:
Worst and Average case: O(n*n), when the array is in reverse order
Best case: O(n), when the array is already sorted
The algorithm is popular in computer graphics, due to its capability to detect some small errors in sorting. 
For example, in an almost sorted array, only two elements need to be swapped, to get a completely sorted array. 
Bubble Sort can fix such errors (ie. sort this array) in linear time.
*/

	public static void bubbleSort(int[] arr) {
	    int i = 0, n = arr.length;
	    boolean swapNeeded = true;
	    while (i < n - 1 && swapNeeded) {
	        swapNeeded = false;
	        for (int j = 1; j < n - i; j++) {
	            if (arr[j - 1] > arr[j]) {
	                int temp = arr[j - 1];
	                arr[j - 1] = arr[j];
	                arr[j] = temp;
	                swapNeeded = true;
	            }
	        }
	        if(!swapNeeded) {
	            break;
	        }
	        i++;
	    }
	}
```