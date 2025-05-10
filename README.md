# Ass6
Sixth assignment:
https://github.com/alonmutzary/Ass6.git  
  
3. output: 14976  
   since we have 2 threads and each one calls baz 10000 times we would expect the program to print 20000 at the end but it printed 14976 (and changes from run to run)  
    it happens because bar++ is not thread safe, therefore some increments are lost when threads interfere with each other.

5. output: 20000  
    the change of the methods baz() and getBar() to be synchronized means that only one thread at a time can run them on the same object.   
    By synchronizing the method, we avoid the problem of lost increments and ensure that every increment is counted correctly to sum up to 20000.  

6. output: 20000  
    I used synchronized(this) to lock only the part of the method that increments bar.  
    This prevents race conditions like the full synchronized method, but gives more control. The output is now 20000 every time.  

7. output: 89291142 61  
    The value is less than 100,000,000 because bar++ is not thread-safe — threads overwrite each other's updates (race condition).  
    The second number is the execution time in milliseconds.  

8. output: 100000000 2266  
    With synchronized(this), the method baz() becomes thread-safe — only one thread at a time can increment bar, so the output is the expected 100000000.  
    the runtime is 2266 which is much slower then unsyncronized.  
