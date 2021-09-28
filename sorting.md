# Bubble sort
* the core idea of bubble sort is that we will continuously "bubble up" the biggest element in the array so that the biggest remaining element ends up towards the end of the array
* if we repeat the above $n$ times, we'll have put each of the $n$ elements in their correct place

## pseudocode##
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

## pseudocode##
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
