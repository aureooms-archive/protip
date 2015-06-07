# Protips

## Python `enumerate`

Please do not write

```py
n = len(mylist)
for i in range(n):
  item = mylist[i]
  print(i, item)
```

Use
```py
for i, item in enumerate(mylist):
  print(i, item)
```

## C++ streams performance

If you do not want your C++ to be slower than python (g++)

### Do not synchronize with the C standard input-output

Put this at the beginning of your main
```c++
std::ios_base::sync_with_stdio(false);
```

### Use `'\n'` instead of `std::endl`

Quoting from [cplusplus.com](http://cplusplus.com)
_**`std::endl`**: inserts a new-line character and flushes the stream. Its behavior is equivalent to calling `os.put('\n')` (or `os.put(os.widen('\n'))`) for character types other than char), and then `os.flush()`._

Note that for `std` *file-like* streams (like `std::cout`) `'\n'` is mapped to the correct platform new line sequence.

### Reference

  - http://stackoverflow.com/questions/24895881/why-is-python-faster-than-c-in-this-case
  - http://codeforces.com/blog/entry/925
  - http://www.cplusplus.com/reference/ios/ios_base/sync_with_stdio/
  - http://www.cplusplus.com/reference/ostream/endl/

## Python 3.3 `yield from`

Since Python 3.3, instead of

```py
for item in iterator : yield item
```

you can write

```py
yield from iterator
```

which can be useful for recursive generators
```py
def count( start ) :
  yield start
  yield from count( start + 1 )
```

## JavaScript `return\n`

Below code [returns `undefined` with probability 1](http://stackoverflow.com/questions/2846283/what-are-the-rules-for-javascripts-automatic-semicolon-insertion-asi).

```js
return
       a &&
       b &&
       c ;
```
Better be writing this

```js
return a &&
       b &&
       c ;
```

## JavaScript `Array.prototype.sort` vs Quicksort


[Simple recursive quicksort implementation seems faster than the default sort for large arrays](https://jsperf.com/quicksort-t/3).



