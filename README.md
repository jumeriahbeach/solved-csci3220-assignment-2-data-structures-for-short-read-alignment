Download Link: https://assignmentchef.com/product/solved-csci3220-assignment-2-data-structures-for-short-read-alignment
<br>
In this assignment, you will manually construct different data structures for short read alignment based on a sample sequence. For some structures, you will use multiple methods to construct them such that you can cross-check your answers. You will then use BWT to search for a query from the sample sequence and answer a question about a property of BWT. Finally, you will write a program to construct a directed graph from short reads and find Eulerian path(s) from it.

<strong>Questions: </strong>

<ol>

 <li>This question is about various data structures for short read alignment. You are given the DNA sequence <em>s</em>=GTAACTGTAGTG$.</li>

</ol>

<ul>

 <li>Construct the suffix trie of <em>s</em>.</li>

 <li>Construct the suffix tree of <em>s</em>. Each non-root node should be labeled with the starting and ending positions of the corresponding sub-sequence in <em>s</em> (first position counted as 1). If the sub-sequence appears multiple times in <em>s</em>, use the starting and ending positions of the first appearance.</li>

 <li>Using the suffix tree constructed in Part b, construct the suffix array of <em>s</em>. Show clearly in every step how you use the suffix tree to construct the suffix array.</li>

 <li>Use another method to construct the suffix array without assisted by the suffix trie or suffix tree. Show your steps clearly. Do not forget to compare your results in Parts c and d.</li>

 <li>Construct the BWT of <em>s</em>, denoted as <em>b</em>, using the suffix array. Show every step clearly.</li>

 <li>Use another way to deduce the <em>b</em> from <em>s</em> without assisted by the suffix trie, suffix tree or suffix array. Do not forget to compare your results in Parts e and f.</li>

 <li>Use <em>b</em> to determine the starting positions of all appearances of query <em>q</em>=GTA in <em>s</em>, if there is any. Construct any auxiliary data structures of the FM index that you need. Show every step. You should not use the input sequence <em>s</em> or its suffix trie/tree directly.</li>

 <li>Suppose you are given a random DNA sequence drawn from the set of all possible DNA sequences of length <em>n</em> with equal probability for each of the 4<em><sup>n </sup></em> Now you append the symbol $ to the end of the sequence and perform BWT. Does the end-of-sequence symbol $ have equal probability to appear in each of the <em>n</em>+1 positions in the BWT output?</li>

</ul>

Explain why.




<ol start="2">

 <li>Write a computer program called <strong>EP</strong> in C, C++, Java or Python for finding an Eulerian path from the graph constructed from a set of input DNA short reads. Your program should take a list of DNA short reads in the form of upper-case strings from stdin (<strong>not</strong> from a file), each on a different line. The input ends with an empty line.</li>

</ol>

You can assume that the input list contains <strong>distinct</strong> DNA sequences <strong>all of the same length</strong> in no particular order. You do not need to check for errors in the inputs.

Your program should then construct a directed graph based on the input short reads. Specifically, each read (of length <em>k</em>) should become an edge of the graph connecting a node representing the length <em>k</em>-1 prefix of it to a node representing the length <em>k</em>-1 suffix of it. For example, the read CAT should become an edge connecting node CA to node AT.

Your program should then find an Eulerian path and output it to the screen (i.e., stdout) in the form of a text string. For example, suppose an Eulerian path involves the traversal from node CA to AT and then from AT to TT, the output should be the text string CATT.

If there are multiple Eulerian paths in the graph, you can output any one of them. If the graph does not contain an Eulerian path, your program should output nothing.

The non-comment portion of your program is expected to contain no more than 250 lines of code.

Here is an expected screen shot when a Java program is run on an example from the lecture notes:

&gt;java EP

ACA

ATA

ATT

CAT

TAC

TAG

TAT

TTA




TATTACATAG




Your program will be graded based on i) whether it can be compiled/run successfully, ii) whether it follows the input/output formats as specified above, iii) its accuracy on a number of test cases and iv) whether the program is well-documented with appropriate comments added to explain the meaning of the code. In view of the large size of our class, for easy grading, you may get zero score if your program cannot be compiled or it does not conform to the input/output formats specified.

[Optional] Output all Eulerian paths in the graph. Each Eulerian path should occupy a separate line in the output in any order.

Here is a screen shot when a sample Java program was run on the same example from the lecture notes:

&gt;java EP

ACA

ATA

ATT

CAT

TAC

TAG

TAT

TTA




TACATATTAG

TACATTATAG

TATTACATAG

TATACATTAG

If your program outputs multiple Eulerian paths, the first one will determine your score for the non-bonus part (40% of the assignment score) while all the output paths together will determine your score for the bonus part. Therefore, if you decide to take this bonus part, please make sure that the first Eulerian path you output is correct.