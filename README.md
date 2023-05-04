Download Link: https://assignmentchef.com/product/solved-csci203-assignment-3
<br>
The tasks in this exercise consist of activities in the areas of <strong>Data Structures and Algorithms, in particular, algorithm design strategies – Greedy Algorithm, Branch and Bound, backtracking and Divide and Conquer</strong>. The exercises cover the topics discussed in topics 5, 6, and 7.

<h1>Question 1 (20.0 marks)</h1>




Consider the following network. With the indicated link costs, use Dijkstra’s shortest-path algorithm to compute the shortest path from c to all network nodes.

<ol start="15">

 <li>a) Show how the algorithm works by computing a table like the one discussed in class. <strong>(15.0 marks)</strong> b) Show all the paths from c to all other network nodes. <strong>(5.0 marks)</strong></li>

</ol>

<h1><img decoding="async" data-recalc-dims="1" data-src="https://i0.wp.com/www.ankitcodinghub.com/wp-content/uploads/2021/08/499.png?w=980&amp;ssl=1" class="aligncenter lazyload" src="data:image/gif;base64,R0lGODlhAQABAAAAACH5BAEKAAEALAAAAAABAAEAAAICTAEAOw==">

 <noscript>

  <img decoding="async" class="aligncenter" src="https://i0.wp.com/www.ankitcodinghub.com/wp-content/uploads/2021/08/499.png?w=980&amp;ssl=1" data-recalc-dims="1">

 </noscript>Question 2 (20.0 marks)</h1>




Consider the following search problem, represented as a graph. Each node is label by a capital letter and the value of a heuristic function is shown in maroon. Each edge is labelled by the cost to traverse that edge. The start state is ‘A’ and the only goal state is ‘G’. Perform the A* search to find the shortest path from node S to node G.




<ol start="5">

 <li>Is the heuristics specified in the problem (shown below) admissible? Justify your answer. If the heuristics is admissible, proceed to answer part (ii). If the heuristics is not admissible, correct it with a sensible value of your choice and proceed to answer part (ii). <strong>(5.0 mark)</strong></li>

</ol>




<ol>

 <li>Perform the A* search to find the shortest path from the start state (S) to the goal state (G).</li>

</ol>

<strong>(15.0 marks)</strong>

<img decoding="async" data-recalc-dims="1" data-src="https://i0.wp.com/www.ankitcodinghub.com/wp-content/uploads/2021/08/136.png?w=980&amp;ssl=1" class="aligncenter lazyload" src="data:image/gif;base64,R0lGODlhAQABAAAAACH5BAEKAAEALAAAAAABAAEAAAICTAEAOw==">

 <noscript>

  <img decoding="async" class="aligncenter" src="https://i0.wp.com/www.ankitcodinghub.com/wp-content/uploads/2021/08/136.png?w=980&amp;ssl=1" data-recalc-dims="1">

 </noscript>

<strong>Part B: (60.0 marks)</strong>




We have discussed greedy algorithm during lectures. A greedy algorithm is an algorithm that recursively construct a set of objects from the smallest possible constituent parts. At each one of the iterations, the algorithm takes the best that it can get right now, without regards for future consequences. The algorithm hopes that by choosing a local optimum at each one of the iterations, it can end up at a global optimum.




In this assignment, you will <strong>write</strong> a program to schedule final examination for the examination department so that no student has two examinations at the same time. The goal of this assignment is to expose you to the implementation of greedy algorithms that solves a problem with constraints. You will use a greedy algorithm to determine an assignment of classes to examination slots (schedules) such that:

<ol>

 <li>No student, enrolled in two subjects, is assigned to the same examination slot (schedule.)</li>

 <li>Any attempt to combine two slots into one would violate rule 1.</li>

</ol>




Input to the program will consist of the name of a data file. This file will contain the following data:

 The number of students enrolled in the current semester  Repeated rows of the following:

o Name of the student and the total number of subjects enrolled o The subject code the student is enrolled in.




A sample of an input file is as follow:

3

Melissa, 4

CSCI203

CSCI235

CSCI222

CSCI205

Bernard, 4

CSCI213

CSCI222

CSCI204

CSCI203

Terrence, 4

CSCI212

CSCI203

CSCI235

CSCI213




The output of the program should be a list of time slots with the subjects whose final examination will be given at that slot and the total number of students taking the final examination in that slot. One possible output is as follow:




Slot 1: CSCI212, CSCI222         3

Slot 2: CSCI204, CSCI235         3

Slot 3: CSCI205, CSCI213         3

Slot 4: CSCI203                         3







<strong>The algorithm: </strong>

<ul>

 <li>Read the enrolment information from the input file. As the records are read, build an adjacency matrix representing the relationships among the students and the subject the students enrol in. You should notice that this adjacency matrix is a graph representing the relationships. Each node of the graph will be a subject taken by at least one student in the current semester. An edge between two nodes will mean there is at least one student taking both subjects. The weight of an edge could be the number of students enrols with both subjects.</li>

 <li>Your aim in solving this problem is to construct a <em>maximal independent set</em> in the graph. This can be achieved by finding an examination schedule satisfying the two constraints mentioned earlier, as follow:

  <ul>

   <li>Construct a candidate list of subjects.</li>

   <li>Order the subjects in descending order by total number of inconnectivity.</li>

   <li>Starting from the subject with the highest number of inconnectivity, create a slot.</li>

   <li>Search for a subject to which it is not connected. If you find one, add the subject to the same slot and remove it from the candidate list.</li>

   <li>Next, try to find another subject that is not connected to any of those already in the time slot. Similarly, if you find one, add the subject to the same slot and remove it from the candidate list. Continue to do so until there is no more un-connected subject can be found.</li>

   <li>Accumulate the total number of students enrolled from the adjacency matrix. (How can you do that? Give it a thought.)</li>

   <li>Repeat steps (iii) through (vi) until all the subjects are removed from the candidate list.</li>

  </ul></li>

</ul>




<ul>

 <li>Note that no pair of time slots can be combined without creating a time conflict with a student. Also note that depending on how you select a subject from the candidate list, there may be different schedule can be formed. Any schedule satisfying the twomentioned constrained will be acceptable.</li>

</ul>




You are allowed to implement your algorithm for Part B using C++, Java, or Python.

For Part A, type your answer for each question in a MS Word or equivalent document format and save it in a pdf formatted file, name your file as YourNameA3-SolPartA.pdf

<ul>

 <li>For Part B, the name of your program should be greedyAlgo.cpp, java, or greedyAlgo.py depending on the programming language that you use to develop your program. Execute your program with the test data provided, that is, A3Data.txt and <strong>screen capture</strong> your output. Next, zip your source code, libraries, readme.txt together with your screen capture and name your file as YourNameA3-SolPartB.zip.</li>

 <li>Zip together YourName-A3-SolPartA.pdf and YourName-A3-SolPartB.zip and name your file as YourName-A3.zip. Do not use your own filename.</li>

 <li>All assignments that do not satisfy the submission requirements listed above will not be evaluated and will be returned to the students with 0 marks.</li>

</ul>