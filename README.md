# DAA
DAA1
Quick Sort
Quick Sort is a widely used sorting algorithm known for its efficiency and simplicity. 
It follows the divide-and-conquer paradigm by selecting a "pivot" element from the array and partitioning 
the other elements into two sub-arrays according to whether they are less than or greater than the pivot. 
Advantages of quick sort are;
Being fast, easy to implement, and in-place, which means that it does not require extra space.
Disadvantages of quick sort are; 
Being unstable, sensitive to the choice of the pivot, and vulnerable to the worst case.

Quicksort's best case occurs when the partitions are as evenly balanced as possible when their sizes either are equal or are within 1 of each other.
analysis
QuickSort is a sorting algorithm based on the Divide and Conquer algorithm that picks an element as a pivot and partitions the given array around the picked pivot by placing the pivot in its correct position in the sorted array.
diagram
![image](https://github.com/akampaian/DAA/assets/108192144/c062b143-490d-4199-b42b-0bfb5db6866b)

Sample Code:
def quick_sort(arr):
    if len(arr) <= 1:
        return arr
    pivot = arr[len(arr) // 2]
    left = [x for x in arr if x < pivot]
    middle = [x for x in arr if x == pivot]
    right = [x for x in arr if x > pivot]
    return quick_sort(left) + middle + quick_sort(right)

Counting Sort
Counting Sort is a non-comparative sorting algorithm that works by counting the number of occurrences 
of each element and using arithmetic to determine the positions of each element in the sorted output.

Advantages of Counting Sort
1.Counting sort generally performs faster than all comparison-based sorting algorithms, such as merge sort and quicksort, if the range of input is of the order of the number of input.
2.Counting sort is easy to code
3.Counting sort is a stable algorithm.
Disadvantages of Counting Sort
1.Counting sort doesn’t work on decimal values.
2.Counting sort is inefficient if the range of values to be sorted is very large.
3.Counting sort is not an In-place sorting algorithm, It uses extra space for sorting the array elements.

Counting Sort Algorithm
1.Declare an auxiliary array countArray[] of size max(inputArray[])+1 and initialize it with 0.
2.Traverse array inputArray[] and map each element of inputArray[] as an index of countArray[] array, i.e., execute countArray[inputArray[i]]++ for 0 <= i < N.
3.Calculate the prefix sum at every index of array inputArray[].
4.Create an array outputArray[] of size N.
5.Traverse array inputArray[] from end and update outputArray[ countArray[ inputArray[i] ] – 1] = inputArray[i]. Also, update countArray[ inputArray[i] ] = countArray[ inputArray[i] ]
diagram
![image](https://github.com/akampaian/DAA/assets/108192144/31b2ddb8-606d-43d5-9c07-37927e29d010)

Sample Code:
def counting_sort(arr):
    max_value = max(arr)
    count = [0] * (max_value + 1)

    for num in arr:
        count[num] += 1

    sorted_arr = []
    for i in range(len(count)):
        sorted_arr.extend([i] * count[i])

    return sorted_arr


Heap Sort
Heap Sort is a comparison-based sorting algorithm that uses a binary heap data structure to build a max-heap or min-heap and then sorts the elements.
The initial set of numbers that we want to sort is stored in an array e.g. [10, 3, 76, 34, 23, 32] and after sorting, 
we get a sorted array [3,10,23,32,34,76] . Heap sort works by visualizing the elements of the array as a special kind of complete binary tree called a heap.
There are two types of heaps:
1.Min-heap 
2.Max-heap.
Advantages of the heap sort
The algorithm is also highly consistent with very low memory usage. No extra memory space is required to work, unlike the Merge Sort or recursive Quick Sort.
Disadvantages
Heap Sort is considered unstable, expensive, and not very efficient when working with highly complex data.

Sample Code:
def heapify(arr, n, i):
    largest = i
    left = 2 * i + 1
    right = 2 * i + 2

    if left < n and arr[left] > arr[largest]:
        largest = left

    if right < n and arr[right] > arr[largest]:
        largest = right

    if largest != i:
        arr[i], arr[largest] = arr[largest], arr[i]
        heapify(arr, n, largest)

def heap_sort(arr):
    n = len(arr)

    for i in range(n // 2 - 1, -1, -1):
        heapify(arr, n, i)

    for i in range(n - 1, 0, -1):
        arr[i], arr[0] = arr[0], arr[i]
        heapify(arr, i, 0)





    

   





    
   















