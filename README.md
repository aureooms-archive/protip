# protips

## enumerate

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
