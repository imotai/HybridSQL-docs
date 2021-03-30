---
title: /Users/chenjing/work/4paradigm/HybridSE/include/codec/row_list.h

---
# /Users/chenjing/work/4paradigm/HybridSE/include/codec/row_list.h

## Namespaces

| Name           |
| -------------- |
| **[hybridse](/hybridse/usage/api/c++/Namespaces/namespacehybridse.md)**  |
| **[hybridse::codec](/hybridse/usage/api/c++/Namespaces/namespacehybridse_1_1codec.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[hybridse::codec::ListV](/hybridse/usage/api/c++/Classes/classhybridse_1_1codec_1_1_list_v.md)** <br>Basic key-value list of HybridSe.  |




## Source code

```cpp
/*
 * row_window_iterator.h
 * Copyright (C) 4paradigm 2021 chenjing <chenjing@4paradigm.com>
 * Licensed under the Apache License, Version 2.0 (the "License");
 * you may not use this file except in compliance with the License.
 * You may obtain a copy of the License at
 *
 *    http://www.apache.org/licenses/LICENSE-2.0
 *
 * Unless required by applicable law or agreed to in writing, software
 * distributed under the License is distributed on an "AS IS" BASIS,
 * WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
 * See the License for the specific language governing permissions and
 * limitations under the License.
 */
#ifndef HYBRIDSE_ROW_LIST_H
#define HYBRIDSE_ROW_LIST_H
#include "codec/row_iterator.h"
namespace hybridse{
namespace codec{
template <class V>
class ListV {
 public:
    ListV() {}
    virtual ~ListV() {}
    virtual std::unique_ptr<ConstIterator<uint64_t, V>> GetIterator() = 0;
    virtual ConstIterator<uint64_t, V> *GetRawIterator() = 0;
    virtual const uint64_t GetCount() {
        auto iter = GetIterator();
        uint64_t cnt = 0;
        while (iter->Valid()) {
            iter->Next();
            cnt++;
        }
        return cnt;
    }

    virtual V At(uint64_t pos) {
        auto iter = GetIterator();
        if (!iter) {
            return V();
        }
        while (pos-- > 0 && iter->Valid()) {
            iter->Next();
        }
        return iter->Valid() ? iter->GetValue() : V();
    }
};
}
}
#endif  // HYBRIDSE_ROW_LIST_H
```


-------------------------------

Updated on 29 March 2021 at 18:02:28 PDT
