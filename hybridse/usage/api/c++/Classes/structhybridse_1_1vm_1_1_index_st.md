---
title: hybridse::vm::IndexSt

---
# hybridse::vm::IndexSt



`#include <catalog.h>`

## Summary


| Public attributes|    |
| -------------- | -------------- |
| **[name](/hybridse/usage/api/c++/Classes/structhybridse_1_1vm_1_1_index_st.md#variable-name)**| std::string <br>index name  |
| **[index](/hybridse/usage/api/c++/Classes/structhybridse_1_1vm_1_1_index_st.md#variable-index)**| uint32_t <br>position of index  |
| **[ts_pos](/hybridse/usage/api/c++/Classes/structhybridse_1_1vm_1_1_index_st.md#variable-ts_pos)**| uint32_t <br>second key column position  |
| **[keys](/hybridse/usage/api/c++/Classes/structhybridse_1_1vm_1_1_index_st.md#variable-keys)**| std::vector< [ColInfo](/hybridse/usage/api/c++/Classes/structhybridse_1_1codec_1_1_col_info.md) > <br>first keys set  |

## Public Attributes

### variable name

```cpp
std::string name;
```

index name 

### variable index

```cpp
uint32_t index;
```

position of index 

### variable ts_pos

```cpp
uint32_t ts_pos;
```

second key column position 

### variable keys

```cpp
std::vector< ColInfo > keys;
```

first keys set 

-------------------------------

Updated on  1 April 2021 at 16:11:23 PDT