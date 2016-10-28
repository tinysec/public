# about fuzz
Fuzz, the general translation into fuzzy test. This contains two aspects, one is fuzzy, the second is testing.    
Many people think that fuzzy is fuzz all, that the randomized data is fuzz. In fact, random! = Fuzz.    
"Test" is the core, randomized data, just a means of testing.    

Since it is testing, testing what? Test is actually a kind of expectation. 
Any inconsistent with the expected, should be regarded as "abnormal."   
Here, the "abnormal", not necessarily lead to the crash usually seen, in fact, the performance level in the logic, that is, some conditions branch,    
How to capture these non-traditional types of "anomaly" is also a good fuzzer need to be considered, which I have not done enough jsfuzzer.    

Usually, this is not consistent with the expected, at the software level, some performance as a bug, there are some design documents outside the side effects.
Vulnerability = vul, some loopholes Although some simple bugs, some loopholes are actually functional characteristics.

The expectations of this test include design expectations and implementation expectations.
For small-scale software, may be able to avoid a lot of problems from the design, but for large-scale software, such as windows,
Code complexity has reached the point where designers can not expect all the state.
Large-scale software division of the collaborative development, because each implementor of the security awareness and the level of inconsistency, will lead to the designer did not anticipate the problem.  

Software or unit of the implementation process, in fact, is a state machine, data input and output analysis, resulting in the state of the transfer.
When the transition to a state has not been processed, or not handled correctly, it produced the aforementioned "abnormal."   

Software system vulnerabilities, or vulnerability of the source of the trigger, in fact, is for the external data analysis.   
All the external input is harmful, when the software black box testing, the focus can be placed on the data throughout the life     cycle.
Where data is generated, how it is transmitted, where it is parsed, and where it is released.    
In the fuzz, we generally only need to be concerned about where the analysis can be,    
Only the late use of the time, only need to care about where the problems arise.    

The more complex the data format, the higher the entropy value, the more prone to error analysis. Manufacturing enough complexity,     but also fuzzer weapons,    
Manufacturing complexity, the most likely to think of is randomization.    
Pure randomization is meaningless, often will be the first layer of the check to block, so we need to split into the smallest unit to test.    

The so-called minimum test cell rule, is not to take the whole system with a test, but need to test which unit, put that unit extracted from the test alone.    
This minimum granularity can be a module, a section, a function, or even a basic block.    
Hierarchical concrete manifestation of many ways, such as the process of testing, we can inject code, the memory test.   
For the kernel test, we can load the driver, using a direct call to test.    

Layering is a very important idea, third-party unit, whether it is code injection, kernel direct call, in fact, are to the black box code an adaptation of the middle layer.    
So that our abnormal data to bypass those unnecessary checks directly passed to the analytical module.   

Such as syscall usually usermode the stub, in the stub itself in a lot of checks and checks, but in fact these checks can be bypassed,    
The direct syscall approach is equivalent to the fuzzer in your code and the target kernel itself, plus an adaptation layer to aid in the passing of the data.    

For the kernel format analysis, we can even use the idea of layer and unit, separate extraction part of the code,
Directly in the user mode to function as a form to test this part of the code, speed up.   

Faced with a large black box system, fuzzer the high cost of time, so we save as much as possible their own time, but this part of the information collection      
Of the time essential, commonly known as "check out the location" to understand where the system analysis of external data, how to use layered thinking, direct testing of the subsystem.     

The whole process is,   
*  xplore the black box system to resolve the external data subsystem,   
*   Hierarchical testing of this subsystem   
*   Capture system due to the analysis of the "abnormal"   
*   Analyze these exceptions.  

However, due to the relationship between time and cost, usually only concerned with some specific performance, such as the debugger to capture the interrupt, verifier capture the BSOD.   

Good fuzzer criteria for judging.
*  Good coverage.   
  Coverage is behind all the test guarantee, how to ensure coverage, but also can say a few days, and here is not expanded.
*   Unbelievably different ideas and testing point of insanity.  
   Tuhao such as google and MS, you can fight the machine. The poor can only think of witchcraft.  
*   Logging and playback system.   
  The run-time generated log, direct replay, is not a streamlined POC.   
*   Capture of non-traditional exception types.   
  In other words, the exception can not be caught, think of ways to know. Which is part of the PIN and DigTool.   
  If you can immediately feedback to the fuzzer system, then the coverage is even higher.   
*   Its own process control.     
  Fuzzer itself to the implementation of their own state, highly controllable. In order to deal with the callback type of fuzz.   

Js-kernel-fuzzer is currently only the third point, and part of the fourth point, but also need more improvements.   
The IDA is still relatively stupid way to reverse, improve coverage, if you have a good way, Ken please tell.   

Other non-essential, but also very useful part.   
*   Can be split into unit tests to support distributed fuzz.   
*   With the playback system and the virtual machine to do the automated streamlining system.    
  Js-kernel-fuzzer is still Ben Benfa, artificial in the streamlining, each time-consuming efforts to streamline the stream before the MSRC, expect to have time to do this under.   

Summary, fuzz is a very useful method, but also a very complex idea.   
Each company itself more and more attention to fuzz, after the difficulty of mining will be more and more high.   
Above, just a little thinking about fuzz of mine.   


When you think you had understood the fuzz, think about it again   




