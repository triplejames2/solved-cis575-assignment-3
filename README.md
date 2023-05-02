Download Link: https://assignmentchef.com/product/solved-cis575-assignment-3
<br>
<ol>

 <li>Below are 12 functions of <em>n </em>(recall that lg (ln) denotes the binary (natural) logarithm):</li>

</ol>

1<em>.</em>3      <em>n</em>2      2<em>n       n</em>√<em>n      n</em>p<span style="text-decoration: line-through">√</span><em>n           n</em>lg(<em>n</em>)<em>n</em>ln(<em>n</em>)(1<em>.</em>001)<em>n             n</em><em>n      n</em>!        <em>n</em>lg(<em>n</em>)2<em>n</em>+7

<em>n</em>

Arrange these functions in non-decreasing order of growth; that is, find an arrangement <em>f</em><sub>1 </sub>≤ <em>f</em><sub>2 </sub>≤ <em>… </em>≤ <em>f</em><sub>12 </sub>of the functions such that <em>f</em><sub>1 </sub>∈ <em>O</em>(<em>f</em><sub>2</sub>), <em>f</em><sub>2 </sub>∈ <em>O</em>(<em>f</em><sub>3</sub>), …<em>f</em><sub>11 </sub>∈ <em>O</em>(<em>f</em><sub>12</sub>). For each <em>i</em>, you should write <em>f<sub>i </sub></em>≡ <em>f<sub>i</sub></em><sub>+1 </sub>if <em>f<sub>i </sub></em>∈ Θ(<em>f<sub>i</sub></em><sub>+1</sub>), but <em>f<sub>i </sub>&lt; f<sub>i</sub></em><sub>+1 </sub>otherwise. You do not need to argue for your answers.

<ol start="2">

 <li>In this exercise we shall employ two data structures:</li>

</ol>

<ul>

 <li>a <em>queue</em>, with three operations:

  <ul>

   <li>IsEmpty?() which returns true iff (if and only if) the queue is empty.</li>

   <li>InsertLast(<em>x</em>) which inserts <em>x </em>at the end of the queue.</li>

   <li>RemoveFirst() which returns the queue’s first element (which is removed from the queue).</li>

   <li>a <em>priority queue</em>, with three operations:</li>

   <li>IsEmpty?() which returns true iff the priority queue is empty.</li>

   <li>Insert(<em>x</em>) which inserts <em>x </em>into the priority queue.</li>

   <li>RemoveMax() which returns (and removes) the priority queue’s <em>largest </em></li>

  </ul></li>

</ul>

The program below takes as input a queue <em>Q </em>and then sorts it (in reverse order), using a priority queue <em>P </em>which we assume is initially empty.

Sort(<em>Q</em>) <strong>while </strong>not Q.IsEmpty?() x ← Q.RemoveFirst()

P.Insert(x) <strong>while </strong>not P.IsEmpty?()

x ← P.RemoveMax()

Q.InsertLast(x) <strong>return </strong>Q

We shall assume that each operation on <em>queues </em>executes in time Θ(1), i.e., constant time (this can be accomplished by a pointer implementation). We shall also assume that priority queues are implemented such that IsEmpty? executes in time Θ(1), whereas Insert and RemoveMax executes in time Θ(lg<em>k</em>) where <em>k </em>is the current size of the priority queue (this can be accomplished by a “heap” implementation, as we shall see later in this course).

Let <em>T</em>(<em>n</em>) be the (worst-case) running time of Sort, given a queue with <em>n </em>elements.

<ol>

 <li>Express <em>T</em>(<em>n</em>) as the sum of two summations (each of the form). You do not need to argue</li>

</ol>

for your answer.

<ol start="2">

 <li>Use (1) to find a function <em>f</em>, as simple as possible, such that the <em>T</em>(<em>n</em>) ∈ Θ(<em>f</em>(<em>n</em>)). You should justify your answer, for example by referring to Theorem 3.28 in <em>Howell</em>.</li>

</ol>

<ol start="3">

 <li>Estimate the running times, in terms of <em>n</em>, of the following three programs. You should give tight bounds, of the form Θ(<em>f</em>(<em>n</em>)) with <em>f </em>as simplified as possible. Justify your answers; this will involve expressing each running time as a sum. (You can assume that arithmetic operations take time in Θ(1), no matter the size of the operands. Recall that the scope of language constructs is determined by indentation, so in (c), <em>k </em>← <em>k </em>∗ 2 is part of the while loop but not of the for )</li>

</ol>

<em>(a)                                                              (b)                                                           (c)</em>

<em>z </em>← 0                                                       <em>z </em>← 0                                                       <em>z </em>← 0

<strong>for </strong><em>k </em>← 1 <strong>to </strong><em>n </em>∗ <em>n                                  </em><strong>for </strong><em>k </em>← 1 <strong>to </strong><em>n </em>∗ <em>n                                 k </em>← 1

<em>q </em>← 1                                                      <em>q </em>← 1                                                 <strong>while </strong><em>k &lt; n</em>

<strong>while </strong><em>q </em>≤ <em>k                                            s </em>← <em>k </em>∗ <em>k                                                  </em><strong>for </strong><em>q </em>← 1 <strong>to </strong><em>k</em>

<em>q </em>← <em>q </em>+ 1                                          <strong>while </strong><em>q </em>≤ <em>s                                                   z </em>← <em>z </em>+ 1

<em>z </em>← <em>z </em>+ 1                                                <em>q </em>← <em>q </em>∗ 2                                           <em>k </em>← <em>k </em>∗ 2

<em>z </em>← <em>z </em>+ 1