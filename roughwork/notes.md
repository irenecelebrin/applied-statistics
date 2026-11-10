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

## Class 4 

### video 1: overlaps 

we set up the experiment. 6 cups, labelled with numbers. 

define all the possible combinations with itertools.combintions (import package in python) 

It does not count the combiations but provides all the combos. 
Why? the assumption is that each combination has the same probability. 

to reproduce this, you could use random.sample(labels, 4)
it takes a random sample of 4 from the lables provided. --> it picks from 1 or the 70 combinations. 

the combs are wrapped in a lis. normally the generator loads one item at the time not to load everything in memory. wrapping in thelist you load everything at the same time. 
The elements of the list look like lists but are tuples (immutable --> can't be manipulated). that's why they are in round brackets. 
why tuple? The computer likes immutable stuff --> it's more efficient with tuples. 

with random.sample() you get a list, not a tuple. 
you can sort a list, not a tuple. 
then you can turn in a set, which can store multiple things (graph brackets). A set does not have an order. 
why using a set? very efficient, you can combine them. you can do different operations. 
you can't add stuff to a set? 


**intersection**

once you have your list of combinations and the set of the random sample, 
you can use intersection. 
It produces the random combinations + the overlap between the random set and that combination. the size of the overlap + which ones. 

How many times is there an overlap of 0? 
somewhere there is a perfect overlap. 

What you need is the size of the overlap. 
How many 2s are there? how many 1s? how many 3s, how many 0s, how many perfect overlaps? 

### video 3: hypothesis testing. 

how do you compute the overlaps? 

print the overlap sizes. why is it meaningful? 
there is only 1 way to select the right comb and 1 of selecting the wrong. 
we can quantify also how wrong you can be. How common is it to have an overlap of 3? 

return unique value and counts: how many 0, 1 and 3 (16), 2(36), 4 (1)

there is a symmetry. 

plot in a bar chart. 
this is similar to a **discrete probability distribution**. 
this tells us how much error we are willing to accept in the experiment results. 

null hypothesis: lady has no special power. she is selecting the cups randomly. 

alternative hypothesis: she can tell the difference 

evidence: if the lady is picking randomly, she had huge probability not to succeed. probbaility is 1/70. 

the probability to selct 3 cups is 16/70 + 1/70. 

see error type 1 (false positive) or error type 2 (false negative = false null hypothesis)

chances of type 1 error is 1/70
chances of type 2 error is ?. 


### video 4: terminology 

results of the experiment: selecting the 4 cups (which 4 cups are selected)

the value you derive from the overlap is a number and you can look

**event** a specific combination. a probability is something you associate with ana event. 

**outcomes** the literal outcome: the 4 cups. We assume that the outcomes have equal probability. 

**Outcome**: lady picks 1,2,3,4
**event**: she gets two cups right. 
**Random variable**: n. of cups in the overlap 
**probability**: probability of an event happening 

Basic probability terminology. 

## Class 5 

### video 1 - probability distribution 

**normal distribution** 
50% of the possibilities fall between 25-74 (first and third quartile)

The curve comes up, goes flat and goes down. the slice is takes vertically, not horizontally. It tends to just up in situations where there is random stuff going on. 

### video 2: Binomial (flipping a coin)

import packages: numpy, matplotlib, scipy.stats, statsmodels 

Ask numpy to generate numbers randomly with binomial. Pseudo-random numbers --> not random, deterministic in reality. But whatever. 

read more on numpy.random.binomial: how many results, probability 
using ( means open interval, ] closed. 

Normally functions give the same value, with the same input. Not all functions work like that. For example the random function. 

### video 3: flipping 2 coins 

use the parameter size = output shape. Default is 1 (one single value is returned)

if you use 1000 it flips the coins 1000 times. 

create bar charts for the results. 

Now change the first number. from 1 to 2. Instad of 1 coin, 2 coins. flipped 1000 times. 

0 = 0 heads and 2 tails 
1 = 1 heads and 1 tail 
2 = 2 heads

if you plot this, you see normal distribution. 


## class 6 

### video 1 - Recap 

**Probability distribution** --> different proportions of each outcome (o heads, 1 or 2)

**Random variable** --> probabilistic variable, you don't know what it's gonna be. Called X or PI 

**Outcome** --> Result of the actual experiment: which values each come has 

**Operation** --> The operation following an outcome which derives the random variable 

**Event** --> A set of outcome. Only one happens, but but the event includes all 3 

### video 2: Individual outcomes 

Before we used numpy random binomial np.random.binomiam

n. of coins you wanna flip, probability of each, how many times you wanna generate results 

Alternative: show individual results. Tell numpty to do it. 
Third argument is a tuple (1000, 2) -- tuples cannot be changed, they are easier to process. --> give a list of 1000 with 2 col. 

The first is one experiment with 1 flip and 3 possibe outcomes, the second has two flips each with 2 possible outcomes. they make up 3 total outcomes. 

- You can get different results re-running the code. 
- we don't care about the order, but we do wanna keep track of which is which. 

This gives us a new view in the results and probabilities 

np.unique to see how many times each combination showed up. 
Unique will create a flat array and create a flat array, so you wanna compute across the axis 0 (rows)

unique values are not perfectly 250 each but similar 
01 is conted as different from 01, you need to combine them. 

you can plot them as they are but not that meaningful. 
it should be 3 otcomes, not 4 (actual outcomes)

bars will even out if you do thething 1 hundred thousand times. 

Importan being clear about outcomes, random variables, what you are actualluy measuring. 

### video 3: hundred coins 

Flip 100 coins. 
How many outcomes are possible? 101 different possible values. 
do a lot of experiments --> you wanna see all possible outcomes. 


If you run the function a hundred million times you still don't see all the possible outcomes. Is there a reason why some values are not showing up? is it random? --> that's why you need to run the experiment a n number of times. 

If you run the experiment a significant number of times, why you don't see some of them??

Plot the numbers --> it shows in the middle there is ~50/51 heads. the most number of outcomes in there, and moving away you get less and less. 

(advice: put tickts at 45 digrees or every 5) --> tidy up things, that's part of the job. 

50 is in the middle. the bar chart is symmetrical around it, although not perfect. Samse as the dice bar chart. 

What is the shape? the line is straight but to what degree? 


### video 4:normal distribution

The shape of the bar chart looks like a bell curve, definitely not a triangle. 

it start flat, goes up in a spike and than spikes down and slows down 

**NORMAL DISTRIBUTION** 

a couple of plots are associated with it, centred at differnt points. if they are taller that are narrower, if shorter, wider.

the **sigma** is the spread form zero. Higher sigma gives you a wider plot. 


**exp** = 2.71 

e to the power of that fraction. (see formula on wikipedia, normal distribution)

**mu** is a number like sigma. 

By default we will use the red line, so when x is 0, sigma is 1. --> default values. 

see in notebook how it was calculated using numpy. 

what you do: 
- you create the functin from the mathematical function to python with numpy. 
- you get a numpy array of x
- you calculate y using the function 
- you plot the data. 

Do it with the dice results. for y use the proportion, not the number or roll. 














