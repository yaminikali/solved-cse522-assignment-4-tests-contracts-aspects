Download Link: https://assignmentchef.com/product/solved-cse522-assignment-4-tests-contracts-aspects
<br>
<h1>Part 1: JUnit Test for DupTree</h1>

Refer to file JUnit.zip containing three files:  BST.java, BST_DupTree_Test.java, and A4_Part1_Console_Output.txt.     The file BST.java contain three classes:  Tree,  DupTree, and TreeIterator.

Your task in this part of the assignment is to develop JUnit tests for the class DupTree.  The file BST_DupTree_Test.java gives the overall outline of the code to be developed by you.

<strong>How to develop </strong>BST_DupTree_Test.java<strong>: </strong>

<ul>

 <li>Create an Eclipse project called BST and import the file java into this project. Right-click on the project and choose New → Other → Java → JUnit → JUnit Test Case.  Click Next and enter the name BST_DupTree_Test.  A skeletal class with this name will be created.  Copy the contents of the class outline given as part of the assignment, and complete the outline of the following methods as indicated below.</li>

 <li>setup(): Build a duptree by inserting <em>25 random numbers</em> in the range.24.   Also record these numbers in a Java ArrayList object.  Sort the array list after all numbers are added.</li>

 <li>check_invariant(): Use <em>assertTrue</em> to check the binary search tree property.   You need to define the boolean ordered() function, as illustrated in Lecture 18 slide #6.</li>

 <li>test_insert(): Create two iterators, one for DupTree and the other for ArrayList, and check using <em>assertTrue</em> that every number returned by one iterator is also returned by the other.   This ensures that insert has inserted all the numbers correctly and without any spurious extras.</li>

 <li>test_delete(): Insert 10 random values into the duptree, each in the range .24.  For each value v:

  <ul>

   <li>Obtain the count associated with v using get_count() – this function is to be written by you in class BST_DupTree_Test.</li>

   <li>Delete v from the duptree and check that the count has decreased by one if v’s original count was more than one; otherwise, check that v is no longer in the duptree.</li>

  </ul></li>

 <li>In the above four methods, generate Console output using out.println in order to log how the tests progressed.</li>

</ul>

Once developed, run the project as a <em>JUnit Test </em>and check that you get an output similar to what is illustrated in the file A4_Part1_Console_Output.txt.    Use this name for your output file as well.

Note:  Since random numbers are inserted into the  duptree, you are likely to have different lists of numbers in your Console output.

<strong><em>What to Submit</em></strong><strong>.<em>  </em></strong>Prepare a top-level directory named <em>A4_Part1_UBITId1_UBITId2 </em>if the assignment is done by a team of two students; otherwise, name it as <em>A4_Part1_UBITId</em> if the assignment is done solo.  (Order the <em>UBITId</em>s in alphabetic order, in the former case.)

In this directory, place the files: BST.java, BST_DupTree_Test.java and your

A4_Part1_Console_Output.txt.  Compress the top-level directory and submit the compressed file using submit_cse522 (grads) or submit_cse410 (undergrads).  Only one submission per team is required.

<h1>Part 2:  Contracts for Trees and Iterator</h1>

Refer to file AbsTree.java which defines binary search trees using AbsTree, Tree, and DupTree classes.    Your task in this part of the assignment is to write contracts for the insert and delete methods of class AbsTree and also for the constructor, the next() and stack_tree_nodes() methods of class AbsTree_Iterator.

Note that the post-conditions for insert(n) and delete(n) need to ensure that the counts are appropriately updated for the object containing the value n.   Hence, it is helpful to introduce in classes Tree and DupTree methods insert and delete which delegate the actual task of insertion and deletion to their respective superclass methods, but add a small amount of code to support the enforcement of post-conditions.

<strong><em>What to Do.</em></strong>  The missing Java codes and contracts are indicated via comments, and these are the places where you need to make changes.   <em>Do not modify other parts of the file. </em>  More specifically, in AbsTree  and DupTree you need to:

<ol>

 <li>Define the boolean methods member(int n) and ordered() in class</li>

 <li>Define Requires() for AbsTree.delete(int n) so that it applies to trees and duptrees.</li>

 <li>Define Ensures() for DupTree.insert(int n) and DupTree.delete(int n) suitably.</li>

</ol>

(You are not required to make any additions to class Tree.)

In AbsTree_Iterator, you need to:

<ol>

 <li>Define Requires() and Contract.Ensures() for the constructor. The former should state that the input tree is ordered and the latter should state that the stack-top has the minimum value in the tree.</li>

 <li>Define Requires() and Contract.Ensures() for next(). The former should state that there are more values in the tree/duptree, and the latter should state that the next value will be the ascending order.</li>

 <li>Define Ensures for stack_tree_nodes() by stating that the next smallest value in the tree/duptree is at the top of the stack.</li>

</ol>

Run AbsTree.java augmented with your contracts and ensure that the program works correctly.  (Run using <em>Run Configurations</em>, not <em>Debug Configurations</em>.)

<strong>Part 3:  Contracts as Aspects </strong>

Install AspectJ as an Eclipse plugin using the update site given in Lecture 20 slide #23:

http://download.eclipse.org/tools/ajdt/410/dev/update




The file A4_Part3.zip contains three files:  MyStack.java, MyStackAspect_Outline.aj, and A4-Part3-Screen-Shot.png.   File MyStack.java contains a monomorphic version of the stack datatype discussed in Lecture 18 slides 43-44.  Also shown (as comments) in class MyStack are the contracts for push and pop and the class invariant.




Your task in this part is to develop a file called MyStackAspect.aj incorporating the stack contracts as an AspectJ <strong><em>aspect</em></strong> called MyStackAspect. Within this aspect, you should define two <strong><em>pointcuts</em></strong> and associated <strong><em>advice</em></strong>, one pointcut for the push contract and the other for the pop contract.  An outline of the code to be developed is given in MyStackAspect_Outline.aj.




<strong>How to develop </strong>MyStackAspect.aj<strong>:    </strong>




<ul>

 <li>In Eclipse, create an AspectJ project by doing: File → New → Project → AspectJ → AspectJ Project.  Enter the name MyStack as the name of the project.</li>

 <li>Right-click on project and import the file java.</li>

 <li>Right-click again on the project and choose New → Other → AspectJ → Aspect. Click Next and enter the name MyStackAspect.  A skeletal aspect with this name will be created.</li>

 <li>Complete its definition as indicated in the outline file. A screen-shot of a sample run is given in the file A4-Part3-Screen-Shot.png.   The sequence diagram shown there provides more detailed guidance on the sequence of actions to be taken in the before/after advice</li>

</ul>




Once developed, set up <strong><em>Debug Configurations</em></strong> for the project, and enter and apply (one by one) the following entries in the <strong><em>Exclusion Filter</em></strong> under the JIVE tab.

org.aspectj.* jdk.*




Enable debugging with JIVE.  Run the project in Debug mode and save the <strong><em>Sequence Diagram</em></strong> in a file called A4_Part3.png.    In a correct run of the program, the Console output should show the number 100 and an exception called java.lang.AssertionError.


