# Numpy Notes

NumPy is a Python library used for working with arrays.

## Installation

```bash
pip install numpy
```
---

## Ways of creating 1D array in numpy
## `array()`

>Syntax - 
numpy.array(object, dtype=None, copy=True, order='K', subok=False, ndmin=0)

```python
import numpy
arr = numpy.array([1,2,3,4,5,6,7])
arr = numpy.array([1,2,3,4,5,6,7], int)
arr = numpy.array([1.3,2.5,3.6,4.2,5.4,6.2,7.6], float)
arr = numpy.array(['a','b'])
arr = numpy.array(['saurabh', 'shubham'], dtype=str)
```

## `linspace()`

> Syntax - 
numpy.linspace(start, stop, num=50, endpoint=True, retstep=False, dtype=None, axis=0)


- start - Starting element.
- stop - Ending element.
- num - Its represents no. of parts, the element should be divided. Default is 50 and It - must be non-negative.
- endpoint - If True, stop is included, If False, stop is not included.
- dtype - The type of output array.

```python
from numpy import *
arr = linspace(start, stop, num=50, endpoint=True)

arr = linspace(1,8)
print(list(arr))

arr1 = linspace(1,8,5)
print(arr1)

op:- [1.0, 2.75, 4D.5, 6.25, 8.0]

arr2 = linspace(1,8,5,endpoint=False)
print(arr2)

op:- [1.0, 2.4, 3.8, 5.199999999999999, 6.6]
```

## `logspace()`

> Syntax - numpy.logspace(start, stop, num=50, endpoint=True,base=10.0, dtype=None, axis=0)

```bash
start - 10**start
stop - 10**stop
base - 10.0

logspace(1, 3)
10**1 = 10
10**3 = 1000
->logspace(10, 1000)
```
```python
arr = logspace(1,8,5)
op:-[10.0, 562.34, 31622.77, 1778279.41, 100000000.0]

arr2 = logspace(1,8,5,endpoint=False)
op:-[10.0, 251.18, 6309.57, 158489.31, 3981071.70]

arr3 = logspace(1,8,5, base=12.0)
op:-[12.0, 928.42, 71831.61, 5557542.43, 429981696.0]
```
## `arange()`

> Syntax - numpy.arange(start, stop, stepsize, dtype=None)

- stepsize - Spacing between values. The default step size is 1.
- dtype - The type of output array.

```python
arr = arange(5)
op:-[0.0, 1.0, 2.0, 3.0, 4.0]

arr2 = arange(1,8,2)
op:-[1, 3, 5, 7]

arr3 = arange(2,8)
op:-[2, 3, 4, 5, 6, 7]
```
## `zeros()`

> Syntax - numpy.zeros(shape, dtype=float, order='C')

- shape - shape of new array. It can be an int which will represent number of elements or can be tuple of int. eg. 5, (5,), (3,1)
- order - Whether to store multi-dimensional data in row-major (C-style) or column-major (Fortran-style) order in memory. It can be C or F.

```python
arr = zeros(5)
op:-[0.0, 0.0, 0.0, 0.0, 0.0]

arr2 = zeros(5,dtype=int)
op:-[0, 0, 0, 0, 0]

arr3 = zeros((1,3))
op:-[array([0., 0., 0.])]

arr3 = zeros((2,3))
op:-[array([0., 0., 0.]), array([0., 0., 0.])]
```

## `ones()`

> Syntax - numpy.ones(shape, dtype=float, order='C')

```python
arr = ones(5)
op:-[1.0, 1.0, 1.0, 1.0, 1.0]

arr2 = ones(5,dtype=int)
op:-[1, 1, 1, 1, 1]

arr3 = ones((1,3))
op:-[array([1., 1., 1.])]

arr3 = ones((2,3))
op:-[array([1., 1., 1.]), array([1., 1., 1.])]
```
---
## Mathematical Operations on Arrays using numpy

```python
arr = array([1,2,3,4])
arr = arr + 5
op:-[6,7,8,9]

arr1 = array([1,2,3,4])
arr2 = array([1,2,3,4])
arr = arr1 + arr2
op:-[2,4,6,8]
```
---
## Comparison operators

```python
from numpy import *
arr1 = array([1,2,3,4,5])
arr2 = array([1,3,3,7,5])

result = arr1 == arr2
op:-[ True False  True False  True]

result = arr1 < arr2
op:-[False  True False  True False]
```
---
## any() and all() Functions

- any() - This function return True, if any one element of the iterable is True. If iterable is empty then returns False.

```python
arr1 = array([1,2,3,4,5])
arr2 = array([1,3,3,7,5])
result = arr1 == arr2
any(result)
op:- True
```

- all() - This function return True, if all element of the iterable are True or iterable is empty.

```python
arr1 = array([1,2,3,4,5])
arr2 = array([1,3,3,7,5])
result = arr1 == arr2
all(result)
op:- False
```
---
## where() Function

> Syntax - numpy.where(condition, expression1, expression2)

```python
arr1 = array([10,20,30,40,50])
arr2 = array([1,3,3,7,5])
result = where(arr1 > arr2, arr1, arr2)
op:- [10,20,30,40,50]

arr1 = array([10,2,7,25,30])
arr2 = array([1,3,30,7,31])

result = where(arr1 > arr2, arr1, arr2)
op:-[10  3 30 25 31]
```
---

## nonzero() Function

`This function is used to determine the positions of elements which are non zero. This function returns an array that contains the indexes of the element of the array which are not equal to zero.`

```python
arr = numpy.array([100,20,0,13,5,0])
result = nonzero(arr)
op:-[0,1,3,4]
```