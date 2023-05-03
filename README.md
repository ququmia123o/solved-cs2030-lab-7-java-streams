Download Link: https://assignmentchef.com/product/solved-cs2030-lab-7-java-streams
<br>
<h1></h1>

<h1>Task Content</h1>

<table width="680">

 <tbody>

  <tr>

   <td colspan="3" width="680"><strong>Java Streams</strong><strong>Topic Coverage</strong>Application of Java Streams<strong>Requirements</strong>Java Streams are to be used for the method implementations as specified in this assignment<strong>The Tasks</strong>There are several tasks in this assignment.For each task, you are to define the appropriate method(s) within the Main class in Main.java. We do this so that you can have your code compiled before running in jshell.<strong>Task 1 — Twin Primes</strong>A prime number is a natural number greater than 1 that is only divisible by 1 and itself. A twin prime is one of a pair of prime numbers with a difference of 2. For example, 41 and 43 are twin primes.Define the method twinPrimes in class Main which takes in an integer n and returns an IntStream comprising of distinct twin primes from 2 to n.

    <table width="607">

     <tbody>

      <tr>

       <td width="607">static IntStream twinPrimes(int n)</td>

      </tr>

     </tbody>

    </table>Save your Main class in the file Main.java.</td>

  </tr>

  <tr>

   <td width="37"> </td>

   <td width="607">jshell&gt; Main.twinPrimes(100).toArray()$.. ==&gt; int[15] { 3, 5, 7, 11, 13, 17, 19, 29, 31, 41, 43, 59, 61, 71, 73 } jshell&gt; Main.twinPrimes(100)$.. ==&gt; <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="a0cac1d6c18ed5d4c9cc8ed3d4d2c5c1cd8ee9ced4f0c9d0c5ccc9cec58499e09492c59296999498">[email protected]</a> jshell&gt; Main.twinPrimes(100).toArray()$.. ==&gt; int[15] { 3, 5, 7, 11, 13, 17, 19, 29, 31, 41, 43, 59, 61, 71, 73 } jshell&gt; Main.twinPrimes(100).count()15jshell&gt; Main.twinPrimes(2).forEach(System.out::println)</td>

   <td width="37"> </td>

  </tr>

 </tbody>

</table>

<table width="606">

 <tbody>

  <tr>

   <td width="606">jshell&gt; Main.twinPrimes(2).count() jshell&gt; Main.twinPrimes(3).forEach(System.out::println) 3</td>

  </tr>

 </tbody>

</table>

<h1>Task 2 — Reverse String</h1>

Complete the method reverse in class Main that takes in a String str and returns the reverse of str.

static String reverse(String str) {    return Stream.&lt;String&gt;of(str.split(“”))…

Save your Main class in the file Main.java.

jshell&gt; Main.reverse(“orange”)

$.. ==&gt; “egnaro”




jshell&gt; Main.reverse(“one two three”)

$.. ==&gt; “eerht owt eno”




jshell&gt; Main.reverse(“”)

$.. ==&gt; “”




jshell&gt; Main.reverse(“the quick brown fox jumps over the lazy dog.”)

$.. ==&gt; “.god yzal eht revo spmuj xof nworb kciuq eht”

<h1>Task 3 — Counting Repeats</h1>

Define the method countRepeats in class Main that takes in a List&lt;Integer&gt; of digits of digits 0 to 9 and returns the number of occurrences of adjacent repeated digits. You may assume that there are at least two elements in the array.

static long countRepeats(List&lt;Integer&gt; list)

For example,

the array {0, <u>1, 1</u>,<u> 1</u>,<u> 1</u>, 2} has one occurrence the array {0, 1, <u>2, 2</u>, 1, <u>2, 2</u>, 1, <u>3, 3</u>, 1} has three occurrences of repeated digits

Save your Main class in the file Main.java.

jshell&gt; Main.countRepeats(List.&lt;Integer&gt;of(0, 1, 1, 1, 1, 2))

$.. ==&gt; 1

jshell&gt; Main.countRepeats(List.&lt;Integer&gt;of(0, 1, 2, 2, 1, 2, 2, 1, 3, 3, 1))

$.. ==&gt; 3

jshell&gt; Main.countRepeats(List.&lt;Integer&gt;of(0, 1, 2, 2, 1, 2, 2, 1, 2, 2, 1)) $.. ==&gt; 3

<h1>Task 4 — One-Dimensional Game of Life</h1>

A one-dimensional Conway’s Game of Life is a population of cells represented in a list where each element represents a cell organism. Each cell may be alive or dead.

Let’s assume a population of nine cells with only one living organism (marked 1; 0 being dead) in the initial state (or generation 1):

[0, 0, 0, 0, 1, 0, 0, 0, 0]

For each generation, a cell is alive or dead depending on its own previous state and the previous states of the two neighbour cells. We adopt the following rule:

For each cell in the population,

If a cell is alive in one generation, it will be dead in the next.

If a cell is dead in one generation, but has one and only one live neighbour cell, it will be alive in the next generation.

Applying the above rules to the initial generation above, we obtain the next generation 2:

<table width="680">

 <tbody>

  <tr>

   <td rowspan="2" width="37">and</td>

   <td width="607">[0, 0, 0, 1, 0, 1, 0, 0, 0]</td>

   <td rowspan="2" width="37"> n)</td>

  </tr>

  <tr>

   <td width="607">Applying the rules again to obtain generation 3:

    <table width="606">

     <tbody>

      <tr>

       <td width="606">[0, 0, 1, 0, 0, 0, 1, 0, 0]</td>

      </tr>

     </tbody>

    </table>Define a generateRule() method that returns the above rule in the form UnaryOperator&lt;List&lt;Integer&gt;&gt;.

    <table width="606">

     <tbody>

      <tr>

       <td width="606">static UnaryOperator&lt;List&lt;Integer&gt;&gt; generateRule()</td>

      </tr>

     </tbody>

    </table>Define the gameOfLife method that takes in a List&lt;Integer&gt; list as the starting population, the rule in the formUnaryOperator&lt;List&lt;Integer&gt;&gt; and the integer number of generations n of the game. The method returns a Stream&lt;String&gt; of the game of life for n (&gt; 0) generations where a list element 0 is represented as a blank space, 1 is represented as an asterisk *.static Stream&lt;String&gt; gameOfLife(List&lt;Integer&gt; list, UnaryOperator&lt;List&lt;Integer&gt;&gt; rule, int

    <table width="606">

     <tbody>

      <tr>

       <td width="606">jshell&gt; Main.gameOfLife(List.of(0,0,0,0,1,0,0,0,0), Main.generateRule(), 4).…&gt;    forEach(System.out::println)**                                       **                                       **                                       * * * jshell&gt; int[] arr = new int[63]arr ==&gt; int[63] { 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0,  … , 0, 0, 0, 0, 0, 0, 0, 0 } jshell&gt; arr[31] = 1$.. ==&gt; 1 jshell&gt; List&lt;Integer&gt; list = Arrays.stream(arr).boxed().collect(Collectors.toList()) list ==&gt; [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0,  … 0, 0, 0, 0, 0, 0, 0, 0, 0] jshell&gt; Main.gameOfLife(list, Main.generateRule(), 32).forEach(System.out::println)**                                       **                                       **                                       * * **                                       **                                       *     * **                                       *   *   **                                       * * * * * * **                                       **                                       *             * **                                       *           *   **                                       * * *         * * * **                                       *       *       **                                       *     * *     * *     * **                                       *   *   *   *   *   *   **                                       * * * * * * * * * * * * * * **                                       **                                       *                             * **                                       *                           *   **                                       * * *                         * * * **                                       *                       *       **                                       *     * *                     * *     * **                                       *   *   *                   *   *   *   **                                       * * * * * * *                 * * * * * * * **                                       *               *               **                                       *             * *             * *             * **                                       *           *   *           *   *           *   **                                       * * *         * * * *         * * * *         * * * **                                       *       *       *       *       *       *       **                                       *     * *     * *     * *     * *     * *     * *     * **                                       *   *   *   *   *   *   *   *   *   *   *   *   *   *   **                                       * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *</td>

      </tr>

     </tbody>

    </table></td>

  </tr>

 </tbody>

</table>

<a href="https://mysoc.nus.edu.sg/">MySoC</a> | <a href="https://docs.comp.nus.edu.sg/cf/">Computing Facilities</a> | <a href="https://www.nus.edu.sg/search/">Search</a> | <a href="https://www.nus.edu.sg/campusmap/">Campus Map</a>

School of Computing, National University of Singapore

<a href="https://www.nus.edu.sg/terms.php">Terms of Use</a> | <a href="https://www.nus.edu.sg/policy.php">Privacy</a> | <a href="https://www.nus.edu.sg/nondiscrim.php">Non-discrimination</a>