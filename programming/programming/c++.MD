```
:{ libraries
    -Standard Library
        Containers
            <array>
                New in C++11 and TR1. Provides the container class template std::array, a container for a fixed sized array.
            <bitset>
                Provides the specialized container class std::bitset, a bit array.
            <deque>
                Provides the container class template std::deque, a double-ended queue.
            <forward_list>
                New in C++11 and TR1. Provides the container class template std::forward_list, a singly linked list.
            <list>
                Provides the container class template std::list, a doubly linked list.
            <map>
                Provides the container class templates std::map and std::multimap, sorted associative array and multimap.
            <queue>
                Provides the container adapter class std::queue, a single-ended queue, and std::priority_queue, a priority queue.
            <set>
                Provides the container class templates std::set and std::multiset, sorted associative containers or sets.
            <stack>
                Provides the container adapter class std::stack, a stack.
            <unordered_map>
                New in C++11 and TR1. Provides the container class template std::unordered_map and std::unordered_multimap, hash tables.
            <unordered_set>
                New in C++11 and TR1. Provides the container class template std::unordered_set and std::unordered_multiset.
            <vector>
                Provides the container class template std::vector, a dynamic array.

        General

            <algorithm>
                Provides definitions of many container algorithms.

            <chrono>
                Provides time elements, such as std::chrono::duration, std::chrono::time_point, and clocks.

            <functional>
                Provides several function objects, designed for use with the standard algorithms.
            <iterator>
                Provides classes and templates for working with iterators.

            <memory>
                Provides facilities for memory management in C++, including the class template std::unique_ptr.
            <stdexcept>
                Contains standard exception classes such as std::logic_error and std::runtime_error, both derived from std::exception.
            <tuple>
                New in C++11 and TR1. Provides a class template std::tuple, a tuple.
            <utility>
                Provides the template class std::pair, for working with object pairs (two-member tuples), and the namespace std::rel_ops, for easier operator overloading.

        Localization

            <locale>
                Defines classes and declares functions that encapsulate and manipulate the information peculiar to a locale.
            <codecvt>
                Provides code conversion facets for various character encodings.
        Strings

            <string>
                Provides the C++ standard string classes and templates.
            <regex>
                New in C++11. Provides utilities for pattern matching strings using regular expressions.

        Streams and Input/Output

            <fstream>
                Provides facilities for file-based input and output. See fstream.
            <iomanip>
                Provides facilities to manipulate output formatting, such as the base used when formatting integers and the precision of floating point values.
            <ios>
                Provides several types and functions basic to the operation of iostreams.
            <iosfwd>
                Provides forward declarations of several I/O-related class templates.
            <iostream>
                Provides C++ input and output fundamentals. See iostream.
            <istream>
                Provides the template class std::istream and other supporting classes for input.
            <ostream>
                Provides the template class std::ostream and other supporting classes for output.
            <sstream>
                Provides the template class std::stringstream and other supporting classes for string manipulation.
            <streambuf>
                Provides reading and writing functionality to/from certain types of character sequences, such as external files or strings.

        Language support

            <exception>
                Provides several types and functions related to exception handling, including std::exception, the base class of all exceptions thrown by the Standard Library.
            <limits>
                Provides the template class std::numeric_limits, used for describing properties of fundamental numeric types.
            <new>
                Provides operators new and delete and other functions and types composing the fundamentals of C++ memory management.
            <typeinfo>
                Provides facilities for working with C++ run-time type information.

        Thread support library

            <thread>
                New in C++11. Provide class and namespace for working with threads.
            <mutex>
                New in C++11. 30.4-1 This section provides mechanisms for mutual exclusion: mutexes, locks, and call once.
            <condition_variable>
                New in C++11. 30.5-1 Condition variables provide synchronization primitives used to block a thread until notified by some other thread that some condition is met or until a system time is reached.
            <future>
                New in C++11. 30.6.1-1 Describes components that a C++ program can use to retrieve in one thread the result (value or exception) from a function that has run in the same thread or another thread.

        Numerics library

            Components that C++ programs may use to perform seminumerical operations.

            <complex>
                The header <complex> defines a class template, and numerous functions for representing and manipulating complex numbers.
            <random>
                Facility for generating (pseudo-)random numbers
            <valarray>
                Defines five class templates (valarray, slice_array, gslice_array, mask_array, and indirect_array), two classes (slice and gslice), and a series of related function templates for representing and manipulating arrays of values.
            <numeric>
                Generalized numeric operations.
        
    -STL: Standard Template Library
        Simple containers
            pair 	The pair container is a simple associative container consisting of a 2-tuple of data elements or objects, called 'first' and 'second', in that fixed order. The STL 'pair' can be assigned, copied and compared. The array of objects allocated in a map or hash_map (described below) are of type 'pair' by default, where all the 'first' elements act as the unique keys, each associated with their 'second' value objects.
            Sequences (Arrays/Linked Lists): ordered collections
            vector 	a dynamic array, like C array (i.e., capable of random access) with the ability to resize itself automatically when inserting or erasing an object. Inserting an element to the back of the vector at the end takes amortized constant time. Removing the last element takes only constant time, because no resizing happens. Inserting and erasing at the beginning or in the middle is linear in time.

            A specialization for type bool exists, which optimizes for space by storing bool values as bits.
            list 	a doubly linked list; elements are not stored in contiguous memory. Opposite performance from a vector. Slow lookup and access (linear time), but once a position has been found, quick insertion and deletion (constant time).
            slist
                a singly linked list; elements are not stored in contiguous memory. Opposite performance from a vector. Slow lookup and access (linear time), but once a position has been found, quick insertion and deletion (constant time). It has slightly more efficient insertion, deletion and uses less memory than a doubly linked list, but can only be iterated forwards. It is implemented in the C++ standard library as forward_list.
            deque (double-ended queue) 	a vector with insertion/erase at the beginning or end in amortized constant time, however lacking some guarantees on iterator validity after altering the deque.
            Container adaptors
            queue 	Provides FIFO queue interface in terms of push/pop/front/back operations.

            Any sequence supporting operations front(), back(), push_back(), and pop_front() can be used to instantiate queue (e.g. list and deque).
            priority queue 	Provides priority queue interface in terms of push/pop/top operations (the element with the highest priority is on top).

            Any random-access sequence supporting operations front(), push_back(), and pop_back() can be used to instantiate priority_queue (e.g. vector and deque). It is implemented using a heap.

            Elements should additionally support comparison (to determine which element has a higher priority and should be popped first).
            stack 	Provides LIFO stack interface in terms of push/pop/top operations (the last-inserted element is on top).

            Any sequence supporting operations back(), push_back(), and pop_back() can be used to instantiate stack (e.g. vector, list, and deque).
            Associative containers: unordered collections
            set 	a mathematical set; inserting/erasing elements in a set does not invalidate iterators pointing in the set. Provides set operations union, intersection, difference, symmetric difference and test of inclusion. Type of data must implement comparison operator < or custom comparator function must be specified; such comparison operator or comparator function must guarantee strict weak ordering, otherwise behavior is undefined. Typically implemented using a self-balancing binary search tree.
            multiset 	same as a set, but allows duplicate elements (mathematical Multiset).
            map 	an associative array; allows mapping from one data item (a key) to another (a value). Type of key must implement comparison operator < or custom comparator function must be specified; such comparison operator or comparator function must guarantee strict weak ordering, otherwise behavior is undefined. Typically implemented using a self-balancing binary search tree.
            multimap 	same as a map, but allows duplicate keys.
            hash_set
            hash_multiset
            hash_map
            hash_multimap 	similar to a set, multiset, map, or multimap, respectively, but implemented using a hash table; keys are not ordered, but a hash function must exist for the key type. These types were left out of the C++ standard; similar containers were standardized in C++11, but with different names (unordered_set and unordered_map).
            Other types of containers
            bitset 	stores series of bits similar to a fixed-sized vector of bools. Implements bitwise operations and lacks iterators. Not a sequence. Provides random access.
            valarray 	Another array data type, intended for numerical use (especially to represent vectors and matrices); the C++ standard allows specific optimizations for this intended purpose. According to Josuttis, valarray was badly designed, by people "who left the [C++ standard] committee a long time before the standard was finished", and expression template libraries are to be preferred.[3] A proposed rewrite of the valarray part of the standard in this vein was rejected, instead becoming a permission to implement it using expression template.[4]
        -Iterators
        -Algorithms
        -Functions
```		