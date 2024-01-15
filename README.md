# This java program is implementation of threads to do linear search in such a way that each thread will compare at most 5 elements.
eg: if there are 10 elements in the array, program creates 2 threads say t1,t2 such that t1 will search from index 0 to 4
and t2 search from 5 to 9 concurrently
## How it works?
### Logic:
  - ask user array size
  - each thread will search 5 elements 
    array will be divided into small array if the size of array is above 5
  - eg: if there are 6 elements, t1 will seach in 1st 5 elemnts and t2 will seach the other 1
  + how will i know how many threads i will need?
      1. make array of objects of the class and the size (number of threads)of that array will be calculated like:
      2. if arraysize>5
          - size of MyThread array = size of the user (array/5)+1 :: if there are 6 elemnts we need 2 threads (integer of 6/5 will give 1 so thats y +1 is used)
           - CHATGPT: use double instead of int and ceil() to get correct size :: if 10 elemenst 10/5 is 2 but above satement will make 3 thread i need only 1 
            - cunstructor of MyThread will have array and the elemnt to search 
           -  run method of MyThread will do searching using linear search on the 5 elemnts
#### how will i know the index of array and pass the divided array?
    for i = 0 to number  of threads
        start index = i*5;
        end index = (i+1)*5 - 1 :: 0 to 4 , 5 to 9
    
#### what if there are 6 elements only?
     end index = 6 - but how to do it?
      CHATGPT: Math.min((i + 1) * 5 - 1, size - 1) will give minimum of 10 and 6 so..
#### how will i pass a 10 elemnt array in 2 parts? as seperate array
- make 2 differnt array(difficult)
- CHATGPT:  Arrays.copyOfRange(array, start, end + 1) so elements are copied from 0 to 4 and passed into new seperate small array to MyThread 
### DONE!
### GOAL:if user enters an array of size 100 there will be 20 threads which will run concorently and search for the element


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
