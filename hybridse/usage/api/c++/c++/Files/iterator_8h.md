---
title: /Users/chenjing/work/4paradigm/HybridSE/include/base/iterator.h

---
# /Users/chenjing/work/4paradigm/HybridSE/include/base/iterator.h

## Namespaces

| Name           |
| -------------- |
| **[hybridse](/hybridse/usage/api/c++/Namespaces/namespacehybridse.md)**  |
| **[hybridse::base](/hybridse/usage/api/c++/Namespaces/namespacehybridse_1_1base.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[hybridse::base::DefaultComparator](/hybridse/usage/api/c++/Classes/structhybridse_1_1base_1_1_default_comparator.md)**  |
| class | **[hybridse::base::AbstractIterator](/hybridse/usage/api/c++/Classes/classhybridse_1_1base_1_1_abstract_iterator.md)** <br>An iterator over a key-value pairs dataset.  |
| class | **[hybridse::base::Iterator](/hybridse/usage/api/c++/Classes/classhybridse_1_1base_1_1_iterator.md)** <br>An iterator over a key-value pairs dataset.  |
| class | **[hybridse::base::ConstIterator](/hybridse/usage/api/c++/Classes/classhybridse_1_1base_1_1_const_iterator.md)** <br>An const iterator over a key-value pairs dataset.  |




## Source code

```cpp
/*
 * Copyright 2021 4Paradigm
 *
 * Licensed under the Apache License, Version 2.0 (the "License");
 * you may not use this file except in compliance with the License.
 * You may obtain a copy of the License at
 *
 *   http://www.apache.org/licenses/LICENSE-2.0
 *
 * Unless required by applicable law or agreed to in writing, software
 * distributed under the License is distributed on an "AS IS" BASIS,
 * WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
 * See the License for the specific language governing permissions and
 * limitations under the License.
 */

#pragma once
#include <stdint.h>

namespace hybridse {
namespace base {

struct DefaultComparator {
    int operator()(const uint64_t a, const uint64_t b) const {
        if (a > b) {
            return -1;
        } else if (a == b) {
            return 0;
        }
        return 1;
    }
};

template <class K, class V, class Ref>
class AbstractIterator {
 public:
    AbstractIterator() {}
    AbstractIterator(const AbstractIterator&) = delete;
    AbstractIterator& operator=(const AbstractIterator&) = delete;
    virtual ~AbstractIterator() {}
    virtual bool Valid() const = 0;
    virtual void Next() = 0;
    virtual const K& GetKey() const = 0;
    virtual Ref GetValue() = 0;
    virtual bool IsSeekable() const = 0;

    virtual void Seek(const K& k) = 0;

    virtual void SeekToFirst() = 0;
};
template <class K, class V>
class Iterator : public AbstractIterator<K, V, V&> {};

template <class K, class V>
class ConstIterator : public hybridse::base::AbstractIterator<K, V, const V&> {
};
}  // namespace base
}  // namespace hybridse
```


-------------------------------

Updated on 29 March 2021 at 18:27:02 PDT
