This is the implementation of trie in python3, you can get the question from [implement-trie-prefix-tree](https://leetcode.com/problems/implement-trie-prefix-tree/solution/).

We use dict to store the value.
```python
self.root = {}
```

When we insert a word, we will find every char in the word from node which is initiated to root.
```python
node = self.root
```
Then we use `setdefault` to get the value by the char as key. If char is not in the node, `node[char]` will be `{}`.

For example, after inserted `test`, the root will be as blow:
```python
{'t': {'e': {'s': {'t': {'#': '#'}}}}}
```

As the implementation of the insert function, when we search a word, we will find each char in the word from the node 
which is initiated to root. If the char does not exit in node, return False, otherwise, continue to search the next char. 
After all chars have been found, we should check if `end_of_word` is included in node, for we may just found the prefix, 
not the word.

The last function is `startsWith`, it is almost the same as `search`. But it does not care about if `end_of_word` is in node.

