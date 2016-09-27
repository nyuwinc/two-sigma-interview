One way of approaching this problem is to sort both arrays, then compare the indices of each word.
```
isAnagram(s1, s2):
  if (s1.length != s2.length):
    return false

  charArray1 = s1.sort()
  charArray2 = s2.sort()

  for i = 0 to charArray1.length:
    if (charArray1[i] != charArray2[i]):
      return false

  return true
```
Time and space complexity will depend on the language your using. For the sake of simplicity, let's assume we're using Merge Sort, a sorting algorithm which operates on a time complexity of O(n log n) and space complexity of O(n). While our for-loop does operate O(n), Merge Sort's algorithm will dominate and the time complexity will follow Merge Sort.

A better way of approaching the problem is to use a HashMap or dictionary or a data structure with key-value pairs. The key will be the letter and value will be the number of times the letter has been "seen". We'll increment the value for every time letter has been seen in the first string and decrement the value for every time the letter has been seen in the second string. Then, we'll go through the dictionary and make sure every key has a value of 0.
```
isAnagram(s1, s2):
  if (s1.length != s2.length):
    return false

  Dictionary = {}

  for i = 0 to s1.length:
    Dictionary[s1[i]]++
    Dictionart[s2[i]]--

  for k,v in Dictionary:
    if (v == 0):
      return false

  return true
```

This would result to a better time complexity of O(n), but we will have a space complexity of O(n).

An even better algorithm would be to use an array. We will have to know whether we're dealing with ASCII or Unicode values. However, for the sake of simplicity, let's assume we're dealing with capital letters from A-Z.
```
isAnagram(s1, s2):
  if (s1.length != s2.length):
    return false

  Array = new Array[26]

  for i = 0 to s1.length:
    letter1 = s1[i] - 65 // dealing with ascii number
    letter2 = s2[i] - 65

    Array[letter1]++
    Array[letter2]--

  for i = 0 to Array.length:
    if (Array[i] != 0):
      return false

  return true
```

While we do have to know whether we're dealing with ASCII or Unicode, this is better than previous algorithms since it has a time complexity of O(n) and a space complexity of O(1).
