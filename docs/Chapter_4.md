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

## 4.2-4.3: Superposition

### What is it?

Superpostion states that when you have _N_ number of independent sources in one circuit, you can essentially isolate those sources and consider their effects one at a time by turning off all the other independent sources. You will need to solve _N_ number of individual circuits. 

**Steps to Solve**
1. Pick one independent source, turn off all other independent voltage sources by shorting them and independent current sources by opening them.
2. Use mesh or nodal analysis (or whatever technique works for you) to find the voltage and/or current. 
3. Go back to the original circuit, pick a different source, repeat step one and two.
4. Solve for current and/or voltage for each indiviudal source until they are none left. Add up all the partial circuits to get the total voltage or current.

### Example Problems
Lets take a look at this problem here from one of the previous midterms, I've highlighted the independent sources:
![Example 1](assets\images\superposition_1.PNG)

- Lets start by choosing to focus on the voltage source, so we shall open the current source thereby turning it off and pretending it does not exist at the moment. **Remember dependent sources do not get shorted or opened, only independent sources**

- Next you can choose to do either Nodal or mesh, I've choose mesh for this particular part 

![Partial_Answer](assets\images\superposition_1_answer.jpg)

- I won't be going over nodal for the time being but you can use these equations to solve for the rest of the answers, the purpose for now is just to illustrate how we would go about doing this sort of problem.

- Next, lets switch back to our original equation and this time focus on the independent current source,causing us to short the voltage source. Then drawing would then look a little like this:

![Partial_Answer](assets\images\superposition_1_answer_2.jpg)

- Again we can choose whatever method we like to solve for the current and the dependent voltage source
- Once we have both our answers for the current, we would sum that to retrieve the total current across the 15 ohm resistor. 

### Useful Links

- Here is one of Nathalia's videos on the subject, very useful:
<iframe width="560" height="315" src="https://www.youtube.com/embed/Ug48VDwBKhM" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

- The Organic Chemistry tutor is another great source for practice: 
<iframe width="560" height="315" src="https://www.youtube.com/embed/EX52BuZxpQM" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## 4.4: Source Transformation

### What is it?

Simply put, source transformation is the process of replacing one source with an equivalent source. Source transfomration allows for Independent current sources to be turned into voltage sources and vice versa. This can be applied to both independent _and_ dependent sources. 




