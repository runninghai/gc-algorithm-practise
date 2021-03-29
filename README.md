# gc-algorithm-practise
This is a repo to implement the gc algrithms in [book](https://book.douban.com/subject/26821357/)

# what should the lib offer
THe lib should offer 
```c++
enum Type {
    int8,
    int32,
    int64,
    bytes,
    ptr
}
class Value {
    private:
        Type type;
        size_t size;
        union {
            int8_t int8;
            int32_t int32;
            int64_t int64;
            char[1] bytes; 
            void* ptr;
        } u;
}
class Object {
    private:
        vector<Type> items;
        vector<Value> values;
}
class Allocator {
    public :
        Allocator(size_t size);
        template<typename T> 
        *T alloc(size_t size);
}
```
two api, the first one is used for creating a memory allocator, it receives a 
size param to init the heap chunk.
the second api is used for mutator to alloc a chunk of memory to store the obj.
I'll support 5 kinds of data types including int8, int32, int64, byte array, pointer
# How to evaluate a gc algrithm
## throughput
The request count of memory applied by mutater is the first point

## max STW time
the max time used for gc 

## heap usage



