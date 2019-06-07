# Analysis of Algorithms

## Exercise I

Give an analysis of the running time of each snippet of
pseudocode with respect to the input size n of each of the following:

```
a)  a = 0   //O(1)
    while (a < n * n * n):  //O(n^3)
      a = a + n * n   //O(1)

ANSWER:
O(1) + O(n^3) * O(1)
1 + (n^3 * 1)
O(n^3)
```

```
b)  sum = 0   //O(1)
    for i in range(n):   //O(n)
      i += 1      //O(1) ok
      for j in range(i + 1, n):   //O(n)
        j += 1      //O(1) ok
        for k in range(j + 1, n):   //O(n)
          k += 1      //O(1) ok
          for l in range(k + 1, 10 + k):    //O(n+10)
            l += 1  O(1)
            sum += 1   O(1)

ANSWER:
O(1)  + O(n) * (O(1) + O(n) * (O(1) + O(n) * (O(1) * O(n+10) * (O(1) + O(1))))
1 +  n + n^2 (1 + n * (1 * n+10 * 2))
1 + n + n^2 + n^3 * 2n + 10
1 + n + n^2 + 2n^4 + 10
O(n^4)
```

```
c)  def bunnyEars(bunnies):
      if bunnies == 0: //O(1)
        return 0   //O(1)
      return 2 + bunnyEars(bunnies-1)   O(n - 1)

ANSWER:
O(1) + O(1) + O(n - 1)
n-1
O(n)
```

## Exercise II

Suppose that you have an _n_-story building and plenty of eggs. Suppose also that an egg gets broken if it is thrown off floor _f_ or higher, and doesn't get broken if dropped off a floor less than floor _f_. Devise a strategy to determine the value of _f_ such that the number of dropped eggs is minimized.

Write out your proposed algorithm in plain English or pseudocode and give the runtime complexity of your solution.

```
1. Start in the middle of the building (n/2)
2. It either breaks, or it does not. The outcome of this drop instantly cuts our problem in half.
3. On each drop, we keep dividing the problem in half and half again until we get to our solution.
4. O(log2 n)
```
