---
title: hybridse::vm::CurrentHistoryWindow

---
# hybridse::vm::CurrentHistoryWindow



`#include <mem_catalog.h>`

## Summary

```cpp
class hybridse::vm::CurrentHistoryWindow;
```

|start_ts....................................current_ts| |................................current history window| current history window is effective window there is no current_history_buffer_ 


|  Public functions|            |
| -------------- | -------------- |
|**[CurrentHistoryWindow](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_current_history_window.md#function-currenthistorywindow)**(const [WindowRange](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_window_range.md) & window_range)|  |
|**[CurrentHistoryWindow](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_current_history_window.md#function-currenthistorywindow)**(const [Window::WindowFrameType](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_window.md#enum-windowframetype) window_frame, uint64_t start_offset, uint64_t max_size)|  |
|**[CurrentHistoryWindow](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_current_history_window.md#function-currenthistorywindow)**(const [Window::WindowFrameType](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_window.md#enum-windowframetype) window_frame, uint64_t start_offset, uint64_t start_rows, uint64_t max_size)|  |
|**[~CurrentHistoryWindow](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_current_history_window.md#function-~currenthistorywindow)**()|  |
|**[PopFrontData](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_current_history_window.md#function-popfrontdata)**()| void  |
|**[BufferData](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_current_history_window.md#function-bufferdata)**(uint64_t key, const [Row](/hybridse/usage/api/c++/Classes/classhybridse_1_1codec_1_1_row.md) & row)| bool  |

## Inherited members

Inherited from [hybridse::vm::HistoryWindow](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_history_window.md)

|  Inherited Public functions|            |
| -------------- | -------------- |
|**[HistoryWindow](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_history_window.md#function-historywindow)**(const [WindowRange](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_window_range.md) & window_range)|  |
|**[~HistoryWindow](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_history_window.md#function-~historywindow)**()|  |
|**[PopEffectiveData](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_history_window.md#function-popeffectivedata)**()| void  |

|**Inherited protected functions **| |
| -------------- | -------------- |
| **[BufferCurrentHistoryBuffer](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_history_window.md#function-buffercurrenthistorybuffer)**(uint64_t key, const [Row](/hybridse/usage/api/c++/Classes/classhybridse_1_1codec_1_1_row.md) & row, uint64_t end_ts)|bool  |
| **[BufferEffectiveWindow](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_history_window.md#function-buffereffectivewindow)**(uint64_t key, const [Row](/hybridse/usage/api/c++/Classes/classhybridse_1_1codec_1_1_row.md) & row, uint64_t start_ts)|bool  |
| **[BufferCurrentTimeBuffer](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_history_window.md#function-buffercurrenttimebuffer)**(uint64_t key, const [Row](/hybridse/usage/api/c++/Classes/classhybridse_1_1codec_1_1_row.md) & row, uint64_t start_ts)|bool  |

|**Inherited protected attributes**| |
| -------------- | -------------- |
| **[window_range_](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_history_window.md#variable-window_range_)**|[WindowRange](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_window_range.md)  |
| **[current_history_buffer_](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_history_window.md#variable-current_history_buffer_)**|[MemTimeTable](/hybridse/usage/api/c++/Namespaces/namespacehybridse_1_1vm.md#typedef-memtimetable)  |


Inherited from [hybridse::vm::Window](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_window.md)

| **Inherited public types** | |
| -------------- | -------------- |
|  **[WindowFrameType](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_window.md#enum-windowframetype)** { kFrameRows, kFrameRowsRange, kFrameRowsMergeRowsRange}| enum|


|  Inherited Public functions|            |
| -------------- | -------------- |
|**[Window](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_window.md#function-window)**()|  |
|**[~Window](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_window.md#function-~window)**()|  |
|**[GetIterator](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_window.md#function-getiterator)**() override| std::unique_ptr< RowIterator > <br>Return the const iterator.  |
|**[GetRawIterator](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_window.md#function-getrawiterator)**()| RowIterator * <br>Return the const iterator raw pointer.  |
|**[PopBackData](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_window.md#function-popbackdata)**()| void  |
|**[GetCount](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_window.md#function-getcount)**()| const uint64_t <br>Returns the number of elements in this list.  |
|**[At](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_window.md#function-at)**(uint64_t pos)| [Row](/hybridse/usage/api/c++/Classes/classhybridse_1_1codec_1_1_row.md) <br>Return a the value of element by its position in the list.  |
|**[GetHandlerTypeName](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_window.md#function-gethandlertypename)**() override| const std::string <br>Return the name of handler and return "TableHandler" by default.  |
|**[instance_not_in_window](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_window.md#function-instance_not_in_window)**() const| const bool  |
|**[set_instance_not_in_window](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_window.md#function-set_instance_not_in_window)**(const bool flag)| void  |
|**[exclude_current_time](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_window.md#function-exclude_current_time)**() const| const bool  |
|**[set_exclude_current_time](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_window.md#function-set_exclude_current_time)**(const bool flag)| void  |

|**Inherited protected attributes**| |
| -------------- | -------------- |
| **[exclude_current_time_](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_window.md#variable-exclude_current_time_)**|bool  |
| **[instance_not_in_window_](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_window.md#variable-instance_not_in_window_)**|bool  |


Inherited from [hybridse::vm::MemTimeTableHandler](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_mem_time_table_handler.md)

|  Inherited Public functions|            |
| -------------- | -------------- |
|**[MemTimeTableHandler](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_mem_time_table_handler.md#function-memtimetablehandler)**()|  |
|**[MemTimeTableHandler](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_mem_time_table_handler.md#function-memtimetablehandler)**(const Schema * schema)|  |
|**[MemTimeTableHandler](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_mem_time_table_handler.md#function-memtimetablehandler)**(const std::string & table_name, const std::string & db, const Schema * schema)|  |
|**[GetTypes](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_mem_time_table_handler.md#function-gettypes)**() override| const [Types](/hybridse/usage/api/c++/Namespaces/namespacehybridse_1_1vm.md#typedef-types) & <br>Return table column Types information.  |
|**[~MemTimeTableHandler](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_mem_time_table_handler.md#function-~memtimetablehandler)**() override|  |
|**[GetSchema](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_mem_time_table_handler.md#function-getschema)**()| const Schema * <br>Return table schema.  |
|**[GetName](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_mem_time_table_handler.md#function-getname)**()| const std::string & <br>Return table name.  |
|**[GetIndex](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_mem_time_table_handler.md#function-getindex)**()| const [IndexHint](/hybridse/usage/api/c++/Namespaces/namespacehybridse_1_1vm.md#typedef-indexhint) & <br>Return the index information.  |
|**[GetIterator](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_mem_time_table_handler.md#function-getiterator)**()| std::unique_ptr< RowIterator > <br>Return the const iterator.  |
|**[GetRawIterator](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_mem_time_table_handler.md#function-getrawiterator)**()| RowIterator * <br>Return the const iterator raw pointer.  |
|**[GetDatabase](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_mem_time_table_handler.md#function-getdatabase)**()| const std::string & <br>Return the name of database.  |
|**[GetWindowIterator](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_mem_time_table_handler.md#function-getwindowiterator)**(const std::string & idx_name)| std::unique_ptr< [WindowIterator](/hybridse/usage/api/c++/Classes/classhybridse_1_1codec_1_1_window_iterator.md) >  |
|**[AddRow](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_mem_time_table_handler.md#function-addrow)**(const uint64_t key, const [Row](/hybridse/usage/api/c++/Classes/classhybridse_1_1codec_1_1_row.md) & v)| void  |
|**[AddFrontRow](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_mem_time_table_handler.md#function-addfrontrow)**(const uint64_t key, const [Row](/hybridse/usage/api/c++/Classes/classhybridse_1_1codec_1_1_row.md) & v)| void  |
|**[PopBackRow](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_mem_time_table_handler.md#function-popbackrow)**()| void  |
|**[PopFrontRow](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_mem_time_table_handler.md#function-popfrontrow)**()| void  |
|**[GetFrontRow](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_mem_time_table_handler.md#function-getfrontrow)**()| const std::pair< uint64_t, [Row](/hybridse/usage/api/c++/Classes/classhybridse_1_1codec_1_1_row.md) > &  |
|**[GetBackRow](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_mem_time_table_handler.md#function-getbackrow)**()| const std::pair< uint64_t, [Row](/hybridse/usage/api/c++/Classes/classhybridse_1_1codec_1_1_row.md) > &  |
|**[Sort](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_mem_time_table_handler.md#function-sort)**(const bool is_asc)| void  |
|**[Reverse](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_mem_time_table_handler.md#function-reverse)**()| void  |
|**[GetCount](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_mem_time_table_handler.md#function-getcount)**()| const uint64_t <br>Returns the number of elements in this list.  |
|**[At](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_mem_time_table_handler.md#function-at)**(uint64_t pos)| [Row](/hybridse/usage/api/c++/Classes/classhybridse_1_1codec_1_1_row.md) <br>Return a the value of element by its position in the list.  |
|**[SetOrderType](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_mem_time_table_handler.md#function-setordertype)**(const [OrderType](/hybridse/usage/api/c++/Namespaces/namespacehybridse_1_1vm.md#enum-ordertype) order_type)| void  |
|**[GetOrderType](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_mem_time_table_handler.md#function-getordertype)**() const| const [OrderType](/hybridse/usage/api/c++/Namespaces/namespacehybridse_1_1vm.md#enum-ordertype)  |
|**[GetHandlerTypeName](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_mem_time_table_handler.md#function-gethandlertypename)**() override| const std::string <br>Return the name of handler and return "TableHandler" by default.  |

|**Inherited protected attributes**| |
| -------------- | -------------- |
| **[table_name_](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_mem_time_table_handler.md#variable-table_name_)**|const std::string  |
| **[db_](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_mem_time_table_handler.md#variable-db_)**|const std::string  |
| **[schema_](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_mem_time_table_handler.md#variable-schema_)**|const Schema *  |
| **[types_](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_mem_time_table_handler.md#variable-types_)**|[Types](/hybridse/usage/api/c++/Namespaces/namespacehybridse_1_1vm.md#typedef-types)  |
| **[index_hint_](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_mem_time_table_handler.md#variable-index_hint_)**|[IndexHint](/hybridse/usage/api/c++/Namespaces/namespacehybridse_1_1vm.md#typedef-indexhint)  |
| **[table_](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_mem_time_table_handler.md#variable-table_)**|[MemTimeTable](/hybridse/usage/api/c++/Namespaces/namespacehybridse_1_1vm.md#typedef-memtimetable)  |
| **[order_type_](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_mem_time_table_handler.md#variable-order_type_)**|[OrderType](/hybridse/usage/api/c++/Namespaces/namespacehybridse_1_1vm.md#enum-ordertype)  |


Inherited from [hybridse::vm::TableHandler](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_table_handler.md)

|  Inherited Public functions|            |
| -------------- | -------------- |
|**[TableHandler](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_table_handler.md#function-tablehandler)**()|  |
|**[~TableHandler](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_table_handler.md#function-~tablehandler)**()|  |
|**[GetTypes](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_table_handler.md#function-gettypes)**() =0| const [Types](/hybridse/usage/api/c++/Namespaces/namespacehybridse_1_1vm.md#typedef-types) & <br>Return table column Types information.  |
|**[GetIndex](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_table_handler.md#function-getindex)**() =0| const [IndexHint](/hybridse/usage/api/c++/Namespaces/namespacehybridse_1_1vm.md#typedef-indexhint) & <br>Return the index information.  |
|**[GetWindowIterator](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_table_handler.md#function-getwindowiterator)**(const std::string & idx_name) =0| std::unique_ptr< [WindowIterator](/hybridse/usage/api/c++/Classes/classhybridse_1_1codec_1_1_window_iterator.md) >  |
|**[GetHanlderType](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_table_handler.md#function-gethanldertype)**() override| const [HandlerType](/hybridse/usage/api/c++/Namespaces/namespacehybridse_1_1vm.md#enum-handlertype)  |
|**[GetPartition](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_table_handler.md#function-getpartition)**(const std::string & index_name)| std::shared_ptr< [PartitionHandler](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_partition_handler.md) >  |
|**[GetHandlerTypeName](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_table_handler.md#function-gethandlertypename)**() override| const std::string <br>Return the name of handler and return "TableHandler" by default.  |
|**[GetOrderType](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_table_handler.md#function-getordertype)**() const| const [OrderType](/hybridse/usage/api/c++/Namespaces/namespacehybridse_1_1vm.md#enum-ordertype)  |
|**[GetTablet](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_table_handler.md#function-gettablet)**(const std::string & index_name, const std::string & pk)| std::shared_ptr< [Tablet](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_tablet.md) >  |
|**[GetTablet](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_table_handler.md#function-gettablet)**(const std::string & index_name, const std::vector< std::string > & pks)| std::shared_ptr< [Tablet](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_tablet.md) >  |


Inherited from [hybridse::vm::DataHandler](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_data_handler.md)

|  Inherited Public functions|            |
| -------------- | -------------- |
|**[DataHandler](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_data_handler.md#function-datahandler)**()|  |
|**[~DataHandler](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_data_handler.md#function-~datahandler)**()|  |
|**[GetSchema](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_data_handler.md#function-getschema)**() =0| const Schema * <br>Return table schema.  |
|**[GetName](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_data_handler.md#function-getname)**() =0| const std::string & <br>Return table name.  |
|**[GetDatabase](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_data_handler.md#function-getdatabase)**() =0| const std::string & <br>Return the name of database.  |
|**[GetHanlderType](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_data_handler.md#function-gethanldertype)**() =0| const [HandlerType](/hybridse/usage/api/c++/Namespaces/namespacehybridse_1_1vm.md#enum-handlertype) <br>Return the type of [DataHandler](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_data_handler.md).  |
|**[GetHandlerTypeName](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_data_handler.md#function-gethandlertypename)**() =0| const std::string <br>Return the name of handler type.  |
|**[GetStatus](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_data_handler.md#function-getstatus)**()| base::Status <br>Return dataset status. Default is hybridse::common::kOk.  |


Inherited from [hybridse::codec::ListV< Row >](/hybridse/usage/api/c++/Classes/classhybridse_1_1codec_1_1_list_v.md)

|  Inherited Public functions|            |
| -------------- | -------------- |
|**[ListV](/hybridse/usage/api/c++/Classes/classhybridse_1_1codec_1_1_list_v.md#function-listv)**()|  |
|**[~ListV](/hybridse/usage/api/c++/Classes/classhybridse_1_1codec_1_1_list_v.md#function-~listv)**()|  |
|**[GetIterator](/hybridse/usage/api/c++/Classes/classhybridse_1_1codec_1_1_list_v.md#function-getiterator)**() =0| std::unique_ptr< [ConstIterator](/hybridse/usage/api/c++/Classes/classhybridse_1_1base_1_1_const_iterator.md)< uint64_t, V > > <br>Return the const iterator.  |
|**[GetRawIterator](/hybridse/usage/api/c++/Classes/classhybridse_1_1codec_1_1_list_v.md#function-getrawiterator)**() =0| [ConstIterator](/hybridse/usage/api/c++/Classes/classhybridse_1_1base_1_1_const_iterator.md)< uint64_t, V > * <br>Return the const iterator raw pointer.  |
|**[GetCount](/hybridse/usage/api/c++/Classes/classhybridse_1_1codec_1_1_list_v.md#function-getcount)**()| const uint64_t <br>Returns the number of elements in this list.  |
|**[At](/hybridse/usage/api/c++/Classes/classhybridse_1_1codec_1_1_list_v.md#function-at)**(uint64_t pos)| V <br>Return a the value of element by its position in the list.  |


## Public Functions

#### function CurrentHistoryWindow

```cpp
inline explicit CurrentHistoryWindow(
    const WindowRange & window_range
)
```


#### function CurrentHistoryWindow

```cpp
inline explicit CurrentHistoryWindow(
    const Window::WindowFrameType window_frame,
    uint64_t start_offset,
    uint64_t max_size
)
```


#### function CurrentHistoryWindow

```cpp
inline explicit CurrentHistoryWindow(
    const Window::WindowFrameType window_frame,
    uint64_t start_offset,
    uint64_t start_rows,
    uint64_t max_size
)
```


#### function ~CurrentHistoryWindow

```cpp
inline ~CurrentHistoryWindow()
```


#### function PopFrontData

```cpp
inline virtual void PopFrontData()
```


**Reimplements**: [hybridse::vm::HistoryWindow::PopFrontData](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_history_window.md#function-popfrontdata)


#### function BufferData

```cpp
inline virtual bool BufferData(
    uint64_t key,
    const Row & row
)
```


**Reimplements**: [hybridse::vm::HistoryWindow::BufferData](/hybridse/usage/api/c++/Classes/classhybridse_1_1vm_1_1_history_window.md#function-bufferdata)


