# This java program is implementation of threads to do linear search in such a way that each thread will compare at most 5 elements.
eg: if there are 10 elements in the array, program creates 2 threads say t1,t2 such that t1 will search from index 0 to 4
and t2 search from 5 to 9 concurrently

## Working And OutPut Of The Program:
    Enter the size of the array: 11
    Enter the elements: 
    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11
    Array : 
    1 2 3 4 5 6 7 8 9 10 11 
    Enter the element to search: 3
    ____________________________________
    Thread 3 Is Searching
    Thread 1 Is Searching
    Thread 2 Is Searching
    Element not found in Thread 3
    Element not found in Thread 2
    Element found at index: 2 (Thread 1)
