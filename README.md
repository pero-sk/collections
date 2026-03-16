# info

A collections library for [Cigale](https://github.com/pero-sk/cigale) providing `Map` and `Set` data structures.

use Cigale v0.2.0 (atleast with commit 4c57ab5 or later)


# collections


---

## Install

Add to your project's `cigale.properties`:

```
[dependencies]
collections = "https://github.com/pero-sk/collections"
```

Then fetch:
```
cigale fetch
```

---

## Usage

```
import stdl.console { cout };
import collections { Map, Set };

func public static main() {
    /" Map "/
    Map m = Map();
    m.set("name", "cigale");
    m.set("version", "0.2.0");
    cout(m.get("name"));        // cigale
    cout(m.get("version"));     // 0.2.0
    cout(m.size()<str>);        // 2
    cout(m.has("name")<str>);   // true
    m.remove("name");
    cout(m.has("name")<str>);   // false

    /" Set "/
    Set s = Set();
    s.add("a");
    s.add("b");
    s.add("a");                 // duplicate -- ignored
    cout(s.size()<str>);        // 2
    cout(s.has("a")<str>);      // true

    /" Set from list "/
    Set blank = Set();
    list nums = [1, 2, 3, 4];
    Set sx = blank.from_list(nums);
    cout(sx.size()<str>);       // 4
}
```

---

## Map

| Method | Description |
|---|---|
| `set(key, value)` | Set a key-value pair |
| `get(key)` | Get value by key, returns `null` if not found |
| `has(key)` | Check if key exists |
| `remove(key)` | Remove a key-value pair |
| `size()` | Number of entries |
| `get_keys()` | Returns list of keys |
| `get_values()` | Returns list of values |
| `entries()` | Returns list of `[key, value]` pairs |
| `merge(other)` | Merge another map in, other's values take priority |
| `from_lists(keys, values)` | Populate map from two lists |
| `clear()` | Remove all entries |

---

## Set

| Method | Description |
|---|---|
| `add(value)` | Add a value, ignored if already present |
| `has(value)` | Check if value exists |
| `remove(value)` | Remove a value |
| `size()` | Number of items |
| `values()` | Returns list of all items |
| `from_list(source)` | Create a new Set from a list, removing duplicates |
| `union(other)` | Returns list of all items from both sets |
| `intersection(other)` | Returns list of items in both sets |
| `difference(other)` | Returns list of items in this set but not in other |
| `is_subset(other)` | Check if every item in this set is in other |
| `is_superset(other)` | Check if this set contains every item in other |
| `clear()` | Remove all items |

---
