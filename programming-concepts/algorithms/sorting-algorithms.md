# Sorting Algorithms

Resources: [https://www.educative.io/blog/python-algorithms-coding-interview](https://www.educative.io/blog/python-algorithms-coding-interview)

## Bubble Sort

Bubble Sort swaps adjacent elements if they are in the incorrect order.

The algorithm will iterate through a list of elements until no more swaps occur, meaning all elements are in the corect order.

**Quadratic Time Complexity**, or O(N^2).

Not very efficient, mainly used as a learning resource.

```
def bubble_sort(list):
    for n in range(len(list)):
        for j in range(0, len(list) - n - 1):
            if list[j] > list[j+1]:
                list[j], list[j+1] = list[j+1], list[j]
```

## Selection Sort

Selection Sort looks at a list of elements as if it were two groups; **sorted **and **unsorted**, with the sorted group coming first in the list.

On each iteration, the algorithm findsthe** smallest **element in the **unsorted **group, and swaps it with the** first **element of the **unsorted **group. Thus it is incrementally adding elements to the end of the **sorted** group.

**Quadratic Time Complexity**, or O(N^2)

More efficient than Bubble Sort but still impractical for large inputs.

```
def selection_sort(list):
    for i in range(len(list)):
        min_index = i
        for j in range(i+1, len(list)):
            if list[min_index] > list[j]:
                min_index = j
        list[i], list[min_index] = list[min_index], list[i]
```

## Insertion Sort

Builds the final array by examining each element and comparing / swapping it with elements to the left.

```
def insertion_sort(list):
    for i in range(1,len(list)):  # Traverse through 1 to len(lst)

        key = list[i]
        j = i - 1

        while j >= 0 and key < list[j]: # Move elements of list greater than key, to one position ahead
            list[j+1] = list[j]
            j -= 1
        list[j + 1] = key
```

**Quadratic Time Complexity - O(N^2) **for worst-case scenarios where the input list is in reverse.

Also not good for large inputs.
