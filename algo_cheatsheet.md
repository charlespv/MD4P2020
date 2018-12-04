# Algo Cheat sheet

## Probe 

```Python
import cProfile
cProfile.run("merge_sort(LIST)")
```

## Sort

### Merge Sort (tri fusion)
  
#### With recursivity

```Python
def merge_sort(a):
    if len(a) > 1: 
        # Diviser
        middle = len(a) // 2
        sa1 = merge_sort(a[:middle])
        sa2 = merge_sort(a[middle:])
        # Combiner
        x = next(sa1, None)
        y = next(sa2, None)
        while x and y:
            if x > y:
                yield y
                y = next(sa2, None)
            else:
                yield x
                x = next(sa1, None)
        if x:
            yield x
            for x in sa1:
                yield x
        if y:
            yield y
            for y in sa2:
                yield y
    else:
        # Résolution immédiate
        if len(a) == 1:
            yield a[0]
```

```Python
LIST = [5,1,9,2,3,7,12,23,34,11,17,13, 23, 9, 16, 14, 33, 27, 18, 22]

list(merge_sort(LIST))
```

#### Without recursivity

```Python
def sum_to(n):
    if n > 0:
        return sum_to(n - 1) + n 
    else:
        return 0
        
print(f'somme de 1 à 10: {sum_to(10)}')


def sum_to3(n):
    accum = 0
    while True:
        if n > 0:
            accum += n
            n -= 1
        else:
            return accum
            
print(sum_to3(10000))
```

### Quick Sort (tri rapide)

```Python
def _quicksort1(A, lo, hi):
    if lo < hi:
        p = partition1(A, lo, hi)
        _quicksort1(A, lo, p - 1)
        _quicksort1(A, p + 1, hi)

def partition1(A, lo, hi):
    pivot = A[hi]
    i = lo - 1
    for j in range(lo, hi):
        if A[j] < pivot:
            if i != j:
                i += 1
                _ = A[i]
                A[i] = A[j]
                A[j] = _
    i += 1
    _ = A[i]
    A[i] = A[hi]
    A[hi] = _
    return i

def quicksort1(A):
    _quicksort1(A, 0, len(A) - 1)
    return A

quicksort1([3,2,4])
```
