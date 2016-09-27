# Problem 1, Answer

One way of approaching the problem is to go through the remaining string for
each of the letters. To do this, you would nest for-loops.
```
isUnique(string):
  for i = 0 to string.length:
    for j = i + 1 to string.length:
      if (string[i] == string[j]):
        return false

  return true
```
This would result to a space complexity of O(1). However, the time complexity of this is O(n^2), which means it's not an efficient algorithm.

A better implementation would use a HashMap or Dictionary or a data structure
with key value pairs to remove the nested loop.
```
isUnique(string):
  Dictionary = {}
  for i = 0 to string.length:
    if (Dictionary[string[i]] == 1):
      return false
    else:
      Dictionary[string[i]] = 1

  return true
```

This would result to a time complexity of O(n), much better than the previous
algorithm. However, the space complexity because O(n).

We can improve this algorithm even further by using an Array. However, we have
to know whether we're dealing with ASCII or Unicode characters. For the sake of simplicity, let's assume we're only working letters A-Z.
```
isUnique(string):
  Array = new Array[26]
  for i = 0 to string.length:
    letter = string[i] - 65 // converting the letter's ascii code to fit array size

    if (Array[letter] != null):
      return false

  return true
```

This is a great algorithm since it uses O(1) space, we know we're always dealing with an array of length 26, and it was done in O(n) time.
