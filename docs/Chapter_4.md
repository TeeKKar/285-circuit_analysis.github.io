---
layout: default
title: Chapter 4
nav_order: 1
parent: Home
permalink: /chapter_4
---
# Chapter 4
{: .no_toc }
Midterm-2
{: .label .label-yellow}

This chapter covers superposition, source transformation, and both Thevenin & Norton theorems. 
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

## Overview

This chapter introduces some very useful techniques for circuit simplification that when used properly can lead to less complex, more efficent, and easier to understand circuits.

## 4.2-4.3: Superposition

### What is it?

Superpostion states that when you have _N_ number of independent sources in one circuit, you can essentially isolate those sources and consider their effects one at a time by turning off all the other independent sources. You will need to solve _N_ number of individual circuits for _N_ number of independent sources. 

**Steps to Solve**
1. Pick one independent source, turn off all other independent voltage sources by shorting them and independent current sources by opening them.
2. Use mesh or nodal analysis (or whatever technique works for you) to find the voltage and/or current. 
3. Go back to the original circuit, pick a different source, repeat step one and two.
4. Solve for current and/or voltage for each indiviudal source until they are none left. Add up all the partial circuits to get the total voltage or current.

### Example Problems
Lets take a look at this problem here from one of the previous midterms, I've highlighted the independent sources:
![Example_2](assets\images\chapter_4\superposition_2.PNG)

- We have two independent sources, one voltage and one source, lets choose to focus on the voltage source first, meaning we open the current source.

- Since we have a voltage source with no current, lets choose to do mesh analysis, I've (poorly drawn) the two meshs in questions:

![partial_answer2_1](assets\images\chapter_4\superposition_2_answer_1.PNG)

```python
A: -10v + 5(i1) + 20(i1 - i2) = 0
B: 20(i2 - i1) + 1(i2) + 3(i2) + 5(i2) = 0
# Further reducing the equations results in:
A: 25(i1) - 20(i2) = 10
B: -20(i2) - 31(i2) = 0
# Solving the system of equations you get:
i1 = 0.82
i2 = 0.53
# use values to solve for v0 across the load resistor
v0 = IR
v0 = (0.53)(5)
v0 = 2.6 
```
- Now lets revert back to the original circuit, and this time choose the current source, our ciruit would now look like this:

![partial_answer2_2](assets\images\chapter_4\superposition_2_answer_2.PNG)

- As you can see, the two parallel resistors can be combined for further simplification, lets combine the circuit and once again choose mesh analysis for simplification:

![partial_answer2_3](assets\images\chapter_4\superposition_2_answer_3.PNG)

```python
A: i2 = -5
B: 4(i1) + (i1 - 5) + 3(i1) + 5(i1) + 2(i1) = 0
# simplifying further leads to
15(i1) + 5 = 0
i1 = -0.33
v0 = 5 * -0.33
v0 = -1.6
```
- Now that we have the partial answers for the voltage across the load resistor, we simply add the two partial answers.

```python
v0 = 2.6 - 1.6
v0 = 1.0
```

Lets look at another problem, this time with a dependent source:
![Example 1](assets\images\chapter_4\superposition_1.PNG)

- Lets start by choosing to focus on the voltage source, so we shall open the current source thereby turning it off and pretending it doesn't exist at the moment. **Remember dependent sources do not get shorted or opened, only independent sources**

- Next you can choose to do either Nodal or mesh, I've choose mesh for this particular part 

![Partial_Answer](assets\images\chapter_4\superposition_1_answer.jpg)

- I won't be going over mesh analysis for the time being but you can use these equations to solve for the rest of the answers, the purpose for now is just to illustrate how we would go about doing this sort of problem.

- Next, lets switch back to our original equation and this time focus on the independent current source,causing us to short the voltage source. Then drawing would then look a little like this:

![Partial_Answer](assets\images\chapter_4\superposition_1_answer_2.jpg)

- Again we can choose whatever method we like to solve for the current and the dependent voltage source
- Once we have both our answers for the current, we would sum that to retrieve the total current across the 15 ohm resistor. 


### Useful Links

- Here is one of Nathalia's videos on the subject, very useful as you can expect these sort of problems on the tests:
<iframe width="560" height="315" src="https://www.youtube.com/embed/Ug48VDwBKhM" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

- ilectureonline is a great source for understanding the fundamentals, he also does a great job in explaining how to solve the circuits as he breaks it down step by step:
<iframe width="560" height="315" src="https://www.youtube.com/embed/0T1zcgs8mek" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe> 

- The Organic Chemistry tutor is another great source for practice: 
<iframe width="560" height="315" src="https://www.youtube.com/embed/EX52BuZxpQM" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## 4.4: Source Transformation

### What is it?

Source transformation is the process of replacing one source with an equivalent source. Source transformation allows for current sources to be turned into voltage sources and vice versa. This can be applied to both independent _and_ dependent sources. 

Steps:
- Recall Ohm's law for a second, Ohm's law states that I = V/R, so if we have a voltage source that is in series with a resitor, we can convert that into a current source that is parallel to the same resistor by dividing the voltage with the resistor.

- Ohm's law also states V = IR, so if we want to convert a current source in parallel with a resistor, we simply multiiply that value of that current source with that resistor to obtain a voltage source in series with that same resistor.

I know, those sentences are tongue twisters but lets take a look at an example to illustrate what I mean

### Examples
Let's start simple, this is one of the problems taken form one of the homework
![example_1](assets\images\chapter_4\sourcetrans_1.PNG)

So we have two current sources - and remember it doesn't have to be an independent source - in parallel with a resistor (which it has to be in order to transform it). Since our objective is to get it to one loop, lets source transform both the sources. I've boxed the two sources that need transforming. **Remember, the direction of the source matters**

![answer-pt1](assets\images\chapter_4\sourcetrans_1_answer_1.PNG)

```python
# Lets transform the independent current source first into a voltage
# To obtain that we multiply 10 amps by 10 ohms resulting in 100 volts
V_transformed = (10)*(10) = 100
# Now lets do the same with the dependent source
# Dependent sources can be a little scary looking cause of the numbers but really it's just the same principle
V_transformed_2 = (2*Vx) * 10
V_transformed_2 = 20*Vx
```

After transforming our circuit looks like this:
![answer-pt2](assets\images\chapter_4\sourcetrans_1_answer_2.PNG)

This allows us to then easily apply KVL/mesh analysis to solve for Vx

### Useful Links

Here is Nathalia's video on source transformation going over one of the problems:
<iframe width="560" height="315" src="https://www.youtube.com/embed/bvLXt4nna80" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Again, ilectureonline is another solid channel for understanding the concepts:
<iframe width="560" height="315" src="https://www.youtube.com/embed/dXOmxR0u0No" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## 4.5 Thevenin's Theorem 

### What is it?

Léon Charles Thévenin was a French dude and Telegraph engineer way back in the 1800s. When working on measuring electrical circuits, he realized that for a circuit containing multiple voltage and current sources along with resistors - and only containing those three components - you can replace all those multiple sources with just one equivalent voltage source in series with an equivalent resistance/resistor. If this sounds sort of like source transformation, it's because source transformation uses/derives from Thevenin's and Norton's theorems.

### How to calculate the Thévenin equivalent circuit    

- We begin by choosing a parallel resistor on whichever side of the circuit, this resistor we choose will be called the "load" resistor. Lets remove the resistor for now (we swap it back in later), leaving the two terminals where the load resitor was open. 

- Once we remove the load resistor, we are left with anyother circuit that we have to find the voltage for. We have three analysis methods at our disposal to find the voltage, so use whichever technique to solve for it. That will become Thévenin voltage.

- Next we have to find the Thévenin equivalent resistance. This one can get a little complicated, because they are two scenarios we have to worry about.

1. When we have only independent sources in the circuit, we can calculate the Thévenin resistance (Rth as it's commonly called) by opening the voltage sources and shorting the current sources similar to how we did it for superposition. Once all the sources are removed you should be left with just the resistors, find the total resistance. **Be extra careful and check if the resistors are in parallel or in series.**

2. When we _do_ infact have dependent sources we have to use the "**poke the possum**" method. Like before get rid of any independent sources but we leave the dependent sources alone. In place of the load resistor, swap it for either a test current source or test voltage source. Typically these test sources are 1mA or 1v respectivley but you can choose whatever value you like. Like we had when calculating the Thévenin voltage, we're left with a typical closed loop circuit. Use whichever method to calculate the current of the ciruit. The Thévenin equivalent resistance becomes the Thévenin equivalent voltage divided by the current we dervied. 

## 4.6: Norton's Theorem 

### What is it?

So it's called Norton's theorem but really two people discovered it, Edward Lawry Norton from Bell Labs and Hans Ferdinand Mayer from Siemens & Halske in 1926 way after Thévenin came up with his theorem. Norton's theorem is the complement of Thévenin's. In source transformation, we said that we can turn a voltage source in series into a current source in parallel, that derives from Norton's theorem. Take the same prerequisites we had for obtaining Thévenin's theorem - has to be a linear circuit, only current, voltage sources and resistors - except this time instead of a equivalent voltage source in series with an equivalent resitor we end up with a equivalent current source in parallel with equivalent resistance. 

### How to calculate Norton's equivalent:

-To calculate the equivalent current,choose a resistor in parallel as your "load" resistor like last time. Get rid of any independent sources and solve for the current this time instead of the voltage.

- The great thing about these theorems is finding the equivalent resistance is the same method for both, including poke the possum. 



