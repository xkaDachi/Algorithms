```java
Complexity
The performance of Radix Sort depends on the stable sorting algorithm chosen to sort the digits.
Here we've used the Radix Sort to sort an array of n numbers in base b. In our case, the base is 10. 
We've applied the Counting Sort d times where d stands for the number of digits. So the time complexity of Radix Sort becomes O(d * (n + b)).
The space complexity is O(n + b) since we have used a variation of Counting Sort as a subroutine here.

public static void sort(int[] numbers) {
    int maximumNumber = findMaximumNumberIn(numbers);
    int numberOfDigits = calculateNumberOfDigitsIn(maximumNumber);
    int placeValue = 1;
    while (numberOfDigits-- > 0) {
        applyCountingSortOn(numbers, placeValue);
        placeValue *= 10;
    }
}

public static void applyCountingSortOn(int[] numbers, int placeValue) {

    int range = 10 // decimal system, numbers from 0-9

    // ...

    // calculate the frequency of digits
    for (int i = 0; i < length; i++) {
        int digit = (numbers[i] / placeValue) % range;
        frequency[digit]++;
    }

    for (int i = 1; i < range; i++) {
        frequency[i] += frequency[i - 1];
    }

    for (int i = length - 1; i >= 0; i--) {
        int digit = (numbers[i] / placeValue) % range;
        sortedValues[frequency[digit] - 1] = numbers[i];
        frequency[digit]--;
    }
    System.arraycopy(result, 0, numbers, 0, length); 
}

```
