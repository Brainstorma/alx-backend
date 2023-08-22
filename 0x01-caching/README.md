# 0x01. Caching

This project contains examples of using caching in Python to improve application performance.

## Tasks

### 0-basic_cache.py

A function that caches the result of a specific function for a given argument. It stores the result in a dictionary and returns the cached value if the argument has already been passed before. Otherwise it will call the function, store the result, and return it.

See [0-basic_cache.py](0-basic_cache.py)

### 1-fifo_cache.py 

Implements a FIFO caching system. Uses a deque to store the cache values with a max size. When full, it will pop out the oldest value and append the new one.

See [1-fifo_cache.py](1-fifo_cache.py)

### 2-lifo_cache.py

Implements a LIFO caching system. Uses a deque to store the cache values with a max size. When full, it will pop out the most recent value and append the new one.

See [2-lifo_cache.py](2-lifo_cache.py) 

### 3-lru_cache.py

Implements an LRU (Least Recently Used) caching system. Stores the cache values in a regular dictionary but tracks access with a doubly linked list. Moves accessed values to the head of the list. When full, deletes the tail node.

See [3-lru_cache.py](3-lru_cache.py)

### 4-mru_cache.py

Implements an MRU (Most Recently Used) caching system. Stores the cache values in a regular dictionary and tracks access with a doubly linked list. Moves accessed nodes to the head. When full, deletes the head node.

See [4-mru_cache.py](4-mru_cache.py)

### 100-lfu_cache.py

Implements an LFU (Least Frequently Used) caching system. Keeps count of how many times a value has been accessed. When full, deletes the value with the lowest count.

See [100-lfu_cache.py](100-lfu_cache.py)



## Tasks To Complete

+ [x] 0. **Basic dictionary**<br/>[0-basic_cache.py](0-basic_cache.py) contains a Python class `BasicCache` that inherits from [`BaseCaching`](base_caching.py) and is a caching system:
  + You must use `self.cache_data` - dictionary from the parent class [`BaseCaching`](base_caching.py).
  + This caching system doesn't have limit.
  + `def put(self, key, item):`:
    + Must assign to the dictionary `self.cache_data` the `item` value for the key `key`.
    + If `key` or `item` is `None`, this method should not do anything.
  + `def get(self, key):`:
    + Must return the value in `self.cache_data` linked to `key`.
    + If `key` is `None` or if the `key` doesn't exist in `self.cache_data`, return `None`.

+ [x] 1. **FIFO caching**<br/>[1-fifo_cache.py](1-fifo_cache.py) contains a Python class `FIFOCache` that inherits from [`BaseCaching`](base_caching.py) and is a caching system:
  + You must use `self.cache_data` - dictionary from the parent class [`BaseCaching`](base_caching.py).
  + You can overload `def __init__(self):` but don't forget to call the parent init: `super().__init__()`.
  + `def put(self, key, item):`:
    + Must assign to the dictionary `self.cache_data` the `item` value for the key `key`.
    + If `key` or `item` is `None`, this method should not do anything.
    + If the number of items in `self.cache_data` is higher than `BaseCaching.MAX_ITEMS`:
      + You must discard the first item put in cache (FIFO algorithm).
      + You must print `DISCARD: ` with the key discarded and following by a new line.
  + `def get(self, key):`:
    + Must return the value in `self.cache_data` linked to `key`.
    + If `key` is `None` or if the `key` doesn't exist in `self.cache_data`, return `None`.

+ [x] 2. **LIFO Caching**<br/>[2-lifo_cache.py](2-lifo_cache.py) contains a Python class `LIFOCache` that inherits from [`BaseCaching`](base_caching.py) and is a caching system:
  + You must use `self.cache_data` - dictionary from the parent class [`BaseCaching`](base_caching.py).
  + You can overload `def __init__(self):` but don't forget to call the parent init: `super().__init__()`.
  + `def put(self, key, item):`:
    + Must assign to the dictionary `self.cache_data` the `item` value for the key `key`.
    + If `key` or `item` is `None`, this method should not do anything.
    + If the number of items in `self.cache_data` is higher than `BaseCaching.MAX_ITEMS`:
      + You must discard the last item put in cache (LIFO algorithm).
      + You must print `DISCARD: ` with the `key` discarded and following by a new line.
  + `def get(self, key):`:
    + Must return the value in `self.cache_data` linked to key.
    + If `key` is `None` or if the `key` doesn't exist in `self.cache_data`, return `None`.

+ [x] 3. **LRU Caching**<br/>[3-lru_cache.py](3-lru_cache.py) contains a Python class `LRUCache` that inherits from [`BaseCaching`](base_caching.py) and is a caching system:
  + You must use `self.cache_data` - dictionary from the parent class [`BaseCaching`](base_caching.py).
  + You can overload `def __init__(self):` but don't forget to call the parent init: `super().__init__()`.
  + `def put(self, key, item):`:
    + Must assign to the dictionary `self.cache_data` the `item` value for the key `key`.
    + If `key` or `item` is `None`, this method should not do anything.
    + If the number of items in `self.cache_data` is higher than `BaseCaching.MAX_ITEMS`:
      + You must discard the least recently used item (LRU algorithm).
      + You must print `DISCARD: ` with the `key` discarded and following by a new line.
  + `def get(self, key):`:
    + Must return the value in `self.cache_data` linked to `key`.
    + If `key` is `None` or if the `key` doesn't exist in `self.cache_data`, return `None`.

+ [x] 4. **MRU Caching**<br/>[4-mru_cache.py](4-mru_cache.py) contains a Python class `MRUCache` that inherits from [`BaseCaching`](base_caching.py) and is a caching system:
  + You must use `self.cache_data` - dictionary from the parent class [`BaseCaching`](base_caching.py).
  + You can overload `def __init__(self):` but don't forget to call the parent init: `super().__init__()`.
  + `def put(self, key, item):`:
    + Must assign to the dictionary `self.cache_data` the `item` value for the key `key`.
    + If `key` or `item` is `None`, this method should not do anything.
    + If the number of items in `self.cache_data` is higher than `BaseCaching.MAX_ITEMS`:
      + You must discard the most recently used item (MRU algorithm).
      + You must print `DISCARD: ` with the `key` discarded and following by a new line
  + `def get(self, key):`:
    + Must return the value in `self.cache_data` linked to `key`.
    + If `key` is `None` or if the `key` doesn't exist in `self.cache_data`, return `None`.

+ [x] 5. **LFU Caching**<br/>[100-lfu_cache.py](100-lfu_cache.py) contains a Python class LFUCache that inherits from [`BaseCaching`](base_caching.py) and is a caching system:
  + You must use `self.cache_data` - dictionary from the parent class [`BaseCaching`](base_caching.py).
  + You can overload `def __init__(self):` but don't forget to call the parent init: `super().__init__()`.
  + `def put(self, key, item):`:
    + Must assign to the dictionary `self.cache_data` the `item` value for the key `key`.
    + If `key` or `item` is `None`, this method should not do anything.
    + If the number of items in `self.cache_data` is higher than `BaseCaching.MAX_ITEMS`:
      + You must discard the least frequency used item (LFU algorithm).
      + If you find more than 1 item to discard, you must use the LRU algorithm to discard only the least recently used.
      + You must print `DISCARD: ` with the `key` discarded and following by a new line.
  + `def get(self, key):`:
    + Must return the value in `self.cache_data` linked to `key`.
    + If `key` is `None` or if the `key` doesn't exist in `self.cache_data`, return `None`.

