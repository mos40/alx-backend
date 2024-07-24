# Caching Algorithms Project

This project explores various caching algorithms in Python.

## Table of Contents

- [Background Context](#background-context)
- [Resources](#resources)
- [Learning Objectives](#learning-objectives)
- [Requirements](#requirements)
- [More Info](#more-info)

## Background Context

In this project, we will delve into different caching algorithms to understand their principles and implementations. Caching is a technique used to store frequently accessed data in a temporary storage area (cache) to reduce access time and improve overall system performance.

## Resources

To prepare for this project, read or watch about the following cache replacement policies:
- [FIFO (First-In-First-Out)](https://en.wikipedia.org/wiki/Cache_replacement_policies#First-in-first-out_(FIFO))
- [LIFO (Last-In-First-Out)](https://en.wikipedia.org/wiki/Cache_replacement_policies#Last-in-first-out_(LIFO))
- [LRU (Least Recently Used)](https://en.wikipedia.org/wiki/Cache_replacement_policies#Least_recently_used_(LRU))
- [MRU (Most Recently Used)](https://en.wikipedia.org/wiki/Cache_replacement_policies#Most_recently_used_(MRU))
- [LFU (Least Frequently Used)](https://en.wikipedia.org/wiki/Cache_replacement_policies#Least-frequently_used_(LFU))

## Learning Objectives

By the end of this project, you should be able to explain the following concepts without relying on external resources:
- What a caching system is
- What FIFO, LIFO, LRU, MRU, and LFU mean in the context of caching
- The purpose of a caching system and its benefits
- Limitations of caching systems and factors that affect their efficiency

## Requirements

### Python Scripts
- All scripts will be interpreted/compiled on Ubuntu 18.04 LTS using python3 (version 3.7).
- Ensure all scripts end with a newline.
- The first line of each script should be `#!/usr/bin/env python3`.
- Follow the `pycodestyle` (version 2.5) guidelines for code style.
- All scripts must be executable.

### Documentation
- Include a `README.md` file at the root of the project folder.
- All modules, classes, and functions should have docstrings that explain their purpose.
- Docstrings should be complete sentences that describe the functionality of the module, class, or function.

### BaseCaching Class
- All caching classes must inherit from `BaseCaching` class defined as follows:

```python
#!/usr/bin/python3
""" BaseCaching module
"""

class BaseCaching():
    """ BaseCaching defines:
      - constants of your caching system
      - where your data are stored (in a dictionary)
    """
    MAX_ITEMS = 4

    def __init__(self):
        """ Initialize
        """
        self.cache_data = {}

    def print_cache(self):
        """ Print the cache
        """
        print("Current cache:")
        for key in sorted(self.cache_data.keys()):
            print("{}: {}".format(key, self.cache_data.get(key)))

    def put(self, key, item):
        """ Add an item in the cache
        """
        raise NotImplementedError("put must be implemented in your cache class")

    def get(self, key):
        """ Get an item by key
        """
        raise NotImplementedError("get must be implemented in your cache class")

