# Bubble sort
* the core idea of bubble sort is that we will continuously "bubble up" the biggest element in the array so that the biggest remaining element ends up towards the end of the array
* if we repeat the above $n$ times, we'll have put each of the $n$ elements in their correct place

## pseudocode
```
def bubble_sort(arr):
    n = len(arr)
    for i in 0...n:
        for j in 0...n-i-1) :
        if arr[j] > arr[j+1]:
            swap(arr, j, j+1)
```

# Insertion sort
* the core idea of insertion sort is that we are building a sorted sub-array at the beginning of the array. Each time through our outer loop, we choose one new element from the unsorted area and *insert* it into the sorted sub-array at the beginning (making room as necessary)
* each time around the outer loop, the sorted sub-array gets 1 element bigger until eventually the sub-array is the whole array!

## pseudocode
```
def insertion_sort(arr):
  n = len(arr)
  for i in 1...n:
    cur = arr[i]
    j = i - 1
    insert_into(arr,cur,i)

def insert_into(arr, num, upper_edge):
    j = upper_edge - 1
    while j >= 0:
      if arr[j] < cur:
        break
      arr[j+1] = arr[j]
      j -= 1
    arr[j+1] = cur
```

# Selection sort
* the core idea of selection sort is to continuously find the smallest remaining element we haven't found yet

## pseudocode
```
def selection_sort(arr):
  n = len(arr)
  for i in range(len(arr)):
    ind_min = i
    for j in i...n:
      if arr[j] < arr[ind_min]:
        ind_min = j
    swap(arr, i, ind_min)
```

# Mergesort
* the core idea of merge sort is that it's easier to split the array in half, sort each half, and then merge the halves

## pseudocode
```
def merge_sort(arr):
  merge_sort_r(arr, 0, len(arr))

def merge_sort_r(arr, low, high):
  mid = (low + high)/2
  merge_sort_r(arr, low, mid)
  merge_sort_r(arr, mid, high)
  merge(arr, low, mid, high)

def merge(arr, low, mid, high):
  new_arr = [None] * (high - low)
  i = low
  j = mid
  k = 0
  while i < mid and j < high:
    if arr[i] < arr[j]:
      arr[k] = arr[i]
      i += 1
    else:
      arr[k] = arr[j]
      j += 1
  # while loop to copy over the rest of the left half

  # while loop to copy over the rest of the right half

  # while loop to copy all the elements of new_arr back 
  # to arr
```


# Quicksort
* the core idea of quicksort is that it's easier to split the array into approximately half by shoving the smallish items to the left side and the biggish items to the right side and then recursively sorting each chunk
* we pick an arbitrary element and "partition" around it

## pseudocode
```
def quicksort(arr):
  quicksort_r(arr, 0, len(arr))

def quicksort(arr, low, high):
  pivot_index = get_pivot(arr, low, high)
  mid = partition(arr, low, high, pivot_index)
  quicksort_r(arr, low, mid)
  quicksort_r(arr, mid, high)
```