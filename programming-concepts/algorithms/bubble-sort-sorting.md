# Bubble Sort (Sorting)

Bubble Sort swaps adjacent elements if they are in the incorrect order.

The algorithm will iterate through a list of elements until no more swaps occur, meaning all elements are in the corect order.

Quadratic Time Complexity, or O(N^2).

Not very efficient, mainly used as a learning resource.

```
def bubble_sort(list):
    for n in range(len(list)):
        for j in range(0, len(list) - n - 1):
            if list[j] > list[j+1]:
                list[j], list[j+1] = list[j+1], list[j]
```
