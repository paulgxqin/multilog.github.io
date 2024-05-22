---
layout: default
title: Patch
permalink: /patch/
---
<h1>Automating the Patching Process</h1>

<h2>Observation</h2>
Different patching strategies could be applied to different program points:
1. Flipping predicates
2. Nullifying function innovations
3. Changing function return values

We call a program point that should be considered during the patching process, if the program point is a
1. Conditional predicate (e.g., jz, jnz, jge, …)
2. Function invocation (i.e., call instruction)
3. Function returning (i.e., ret instruction)


<h2>Challenges</h2>
1. How to concretize the PMP execution results, i.e., generating directly runnable unleashed malwares (w/o QEMU).

2. How to automatically identify the patching strategy for each individual program point? Note that the searching space is huge when considering the combination. 
* There are n program points (~300 in one malware)
* We have m patching strategies for each program point (3 strategies) $(ax^2 + bx + c = 0)$
* In total, we can have $m^n$ potential patching versions in the searching space. ($3^{300}=10^{143}$)

<h2>Solution</h2>
1. Combining PMP with static rewriting. 
<a href="https://ieeexplore.ieee.org/document/9519407">StochFuzz (SP’21)</a> is a stochastic binary rewriting technique that can statically rewrite arbitrary binaries with soundness guarantee. 

2. The problem can be reduced as a searching problem which tries to find a proper patching version (among a huge number of potential candidates) that can unleashing malicious payload.
* We leverage fuzzing, a well-developed program testing technique.
In the context of program testing, fuzzing intelligently generates program inputs to achieve high code coverage. 
In our context, fuzzing intelligently selects patching strategy for each program point to unleash malicious payload. 

<h2>Patching Results</h2>
Our tool generated 149 patched versions for 59 malware instances. We manually verified that all the patched versions expose meaningful payloads.
