# NOTES

## Class 1 

### Learning outcomes 

- understand probabilistic (sthocastic) nature of the world 

- be able to source the packages and documentation to investigate specific issues

-  find appropriate solutions 

-  be able to perform a statistical test on a dataset 


### Assessment brief 

- create repo, ipynb file and agents.md and submit by Sep 30 
- work regularly on the assignment 
- 4 problems to showcase learning outcomes have been reached 

Final deadline: 20 December 

### Set up git repo and codespace / IDE 

Deadline to submit repo: 30 September 

Free to use codespaces / VS code / other IDEs 


## Class 2


### Agents 

AGENTS.md 

It's a context file you put in the root of your repo, it provides info to guide the work of your agents. 
They will check that the file has been like that since day 1 --> so peple are not just having agents make the stuff for them. 

### Readme 

- what the repo includes 
- Getting started/Requirements: software required to run the repo /how to get started 
- About the code: 
    - quick look: write about the notebook and what it includes, what the code does 
    - running the code 
- About the author: write about you (the author)

### executing cells 

- remember to restart the kernel and run everything to avoid errors in order of execition
- remember to commit final notebook with outputs (restart + run)


## Class 3 

### Video 1 - lady testing tea problem 

Very famous old problem. Described by Fisher, considered the father of moderns statistical testing. 
Also created the iris dataset. 
A lady says that she can taste wheter the tea or the milk was put first in the cup. 
uses hypothiesis and test and designs and experiment. and wants to find limitations. 
Uses Double blind experiment: person is blind and person gathering the data is also blind to avoid bias. --> introduces more randomness. 

### Video 2 - match comb 

Use python to simulate the experiment. 
Math is already of python standard library, nothing to install. 
random helps generate random numbers 
numpy to deal with data and pyplot to plot it

Consider **permitations** and **combinations**
considering the set {a,b,c}
**permutations**: permutation of a set is the ordering of its elements. abc, bac, cab, bca... 

**combinations** a selection of k elements from a set of size n. the same element cannot be selected twice. Order does not matter.
{a,b}, {a, c}, {b,c} are the possible combinatons. 

Create variable for total cups, cups with milk first and tea first. 

math.comb helps find the number of combinations where 4 cups of a total 8 can be picked

labels: 12345678

placeholeers _ (8 possibilities) _ (7 pos) _ (6 pos) _ (5 pos) 

for every possibility of 1st placeholders there are 7, 6, 5 other possibilities 

multiply: 8 * 7 * 6 * 5 = 1680 

more than 70 generated with math. Why? 

### Video 3 - counting combinations 

70 perfectly divides in 1680. 
1680/70 = 24 

different ordering of the same 4 numbers will account for a unit in 1680. 
it could be 4258 or 8254 or whatever. 
we don't care aboiut that. 
1680 are permutations --> how many different ways for ordering. 
70 are combinations. math.comb() 

you can use math.factorial to find permuations and combinations. and the changes of selecting randomly the cups of tea. 

There is only 1/70 chance to get the right answer. 

Look at factorial amd combinations. 




