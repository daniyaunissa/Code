# Dynamic Multilevel Caching System

## Overview
This is a Python implementation of a dynamic multilevel caching system that supports LRU and LFU eviction policies. It allows adding/removing cache levels, and handles data retrieval and insertion efficiently.

## Features
- Multiple cache levels with configurable size and eviction policies (LRU or LFU).
- Dynamic management of cache levels.
- Thread-safe operations.
- Efficient data retrieval and movement across cache levels.

## Usage
1. **Add Cache Levels:**
   ```python
   manager.add_cache_level(size, 'LRU')  # or 'LFU'

2.Put Data:
 
 manager.put(key, value)

3.Get Data:

value = manager.get(key)

4.Remove Cache Level:

manager.remove_cache_level(level_index)

5.Display Cache State:

manager.display_cache()

Example

manager = CacheManager()


manager.add_cache_level(3, 'LRU')


manager.add_cache_level(2, 'LFU')

manager.put("A", "1")


manager.put("B", "2")


manager.put("C", "3")

print(manager.get("A"))  # Returns "1"


manager.put("D", "4")   # L1 is full, evicts LRU 


print(manager.get("C"))  # Fetches from L2 and promotes to L1


manager.display_cache()

