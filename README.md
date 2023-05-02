Download Link: https://assignmentchef.com/product/solved-comp-2210-assignment-2-collection-selector
<br>



This assignment focuses on implementing the methods of a class much like java.util.Collections. The Selector.java file defines a class with static methods that implement polymorphic algorithms that operate on and/or return Collections. Each method of Selector is very clearly specified, is independent of the other methods in the class, and is designed to provide relatively simple functionality. So, this is a great context for practicing what we’ve been discussing in lecture – generalized programming and test-based verification.

<h1>The Selector class</h1>

You must correctly implement all the method bodies of the provided Selector class. Your implementation must adhere <em>exactly </em>to the API of the Selector class, as described in the provided source code comments and as described below.

<strong>public class </strong><strong>Selector </strong>{ <strong>public static </strong>&lt;T&gt; T min(Collection&lt;T&gt; c, Comparator&lt;T&gt; comp) <strong>public static </strong>&lt;T&gt; T max(Collection&lt;T&gt; c, Comparator&lt;T&gt; comp) <strong>public static </strong>&lt;T&gt; T kmin(Collection&lt;T&gt; c, <strong>int </strong>k, Comparator&lt;T&gt; comp) <strong>public static </strong>&lt;T&gt; T kmax(Collection&lt;T&gt; c, <strong>int </strong>k, Comparator&lt;T&gt; comp) <strong>public static </strong>&lt;T&gt; Collection&lt;T&gt; range(Collection&lt;T&gt; c, T low, T high,

Comparator&lt;T&gt; comp)

<strong>public static </strong>&lt;T&gt; T ceiling(Collection&lt;T&gt; c, T key, Comparator&lt;T&gt; comp) <strong>public static </strong>&lt;T&gt; T floor(Collection&lt;T&gt; c, T key, Comparator&lt;T&gt; comp)

}

The sections that follow provide details of each method’s behavior as well as specific examples.

The <strong>min </strong>method.

This method selects the minimum value from a given collection, as defined by a given comparator. If either the collection or comparator is null, this method throws an IllegalArgumentException. If the collection is empty, the method throws a NoSuchElementException. The collection must not be changed by this method.

<em>Examples:</em>

<table width="608">

 <tbody>

  <tr>

   <td width="118">T</td>

   <td width="212">c</td>

   <td width="162">comp</td>

   <td width="116">&lt;T&gt;min(c, comp)</td>

  </tr>

  <tr>

   <td width="118">Integer</td>

   <td width="212">[2, 8, 7, 3, 4]</td>

   <td width="162"><em>ascending order</em></td>

   <td width="116">2</td>

  </tr>

  <tr>

   <td width="118">Integer</td>

   <td width="212">[5, 9, 1, 7, 3]</td>

   <td width="162"><em>descending order</em></td>

   <td width="116">9</td>

  </tr>

  <tr>

   <td width="118">Integer</td>

   <td width="212">[8, 7, 6, 5, 4]</td>

   <td width="162"><em>ascending order</em></td>

   <td width="116">4</td>

  </tr>

  <tr>

   <td width="118">(String, Integer)</td>

   <td width="212">[(A,5), (B,4), (C,3), (D,2), (E, 1)]</td>

   <td width="162"><em>ascending by String field</em></td>

   <td width="116">(A,5)</td>

  </tr>

  <tr>

   <td width="118">(String, Integer)</td>

   <td width="212">[(A,5), (B,4), (C,3), (D,2), (E, 1)]</td>

   <td width="162"><em>ascending by Integer field</em></td>

   <td width="116">(E,1)</td>

  </tr>

 </tbody>

</table>

1

The <strong>max </strong>method.

This method selects the maximum value from a given collection, as defined by a given comparator. If either the collection or comparator is null, this method throws an IllegalArgumentException. If the collection is empty, the method throws a NoSuchElementException. The collection must not be changed by this method.

<em>Examples:</em>

<table width="611">

 <tbody>

  <tr>

   <td width="118">T</td>

   <td width="212">c</td>

   <td width="162">comp</td>

   <td width="118">&lt;T&gt;max(c, comp)</td>

  </tr>

  <tr>

   <td width="118">Integer</td>

   <td width="212">[2, 8, 7, 3, 4]</td>

   <td width="162"><em>ascending order</em></td>

   <td width="118">8</td>

  </tr>

  <tr>

   <td width="118">Integer</td>

   <td width="212">[5, 9, 1, 7, 3]</td>

   <td width="162"><em>descending order</em></td>

   <td width="118">1</td>

  </tr>

  <tr>

   <td width="118">Integer</td>

   <td width="212">[8, 7, 6, 5, 4]</td>

   <td width="162"><em>ascending order</em></td>

   <td width="118">8</td>

  </tr>

  <tr>

   <td width="118">(String, Integer)</td>

   <td width="212">[(A,5), (B,4), (C,3), (D,2), (E, 1)]</td>

   <td width="162"><em>ascending by String field</em></td>

   <td width="118">(E,1)</td>

  </tr>

  <tr>

   <td width="118">(String, Integer)</td>

   <td width="212">[(A,5), (B,4), (C,3), (D,2), (E, 1)]</td>

   <td width="162"><em>ascending by Integer field</em></td>

   <td width="118">(A,5)</td>

  </tr>

 </tbody>

</table>

The <strong>kmin </strong>method.

This method selects the <em>k<sup>th </sup></em>minimum value from a given collection, as defined by a given comparator. A value is the <em>k<sup>th </sup></em>minimum if there are exactly <em>k</em>−1 values less than it in the collection. If either the collection or comparator is null, this method throws an IllegalArgumentException. If the collection is empty or if there is no <em>k<sup>th </sup></em>minimum value, this method throws a NoSuchElementException. Note that there is no <em>k<sup>th </sup></em>minimum value if <em>k </em>is less than 1, <em>k </em>is greater than the number of elements in the collection, or if <em>k </em>is greater than the number of distinct values in the collection. The collection must not be changed by this method.

<em>Examples:</em>

<table width="653">

 <tbody>

  <tr>

   <td width="118">T</td>

   <td width="212">c</td>

   <td width="23">k</td>

   <td width="162">comp</td>

   <td width="138">&lt;T&gt;kmin(c, k, comp)</td>

  </tr>

  <tr>

   <td width="118">Integer</td>

   <td width="212">[2, 8, 7, 3, 4]</td>

   <td width="23">1</td>

   <td width="162"><em>ascending order</em></td>

   <td width="138">2</td>

  </tr>

  <tr>

   <td width="118">Integer</td>

   <td width="212">[5, 9, 1, 7, 3]</td>

   <td width="23">2</td>

   <td width="162"><em>descending order</em></td>

   <td width="138">7</td>

  </tr>

  <tr>

   <td width="118">Integer</td>

   <td width="212">[8, 7, 6, 5, 4]</td>

   <td width="23">3</td>

   <td width="162"><em>ascending order</em></td>

   <td width="138">6</td>

  </tr>

  <tr>

   <td width="118">(String, Integer)</td>

   <td width="212">[(A,5), (B,4), (C,3), (D,2), (E, 1)]</td>

   <td width="23">4</td>

   <td width="162"><em>ascending by String field</em></td>

   <td width="138">(D,2)</td>

  </tr>

  <tr>

   <td width="118">(String, Integer)</td>

   <td width="212">[(A,5), (B,4), (C,3), (D,2), (E, 1)]</td>

   <td width="23">2</td>

   <td width="162"><em>ascending by Integer field</em></td>

   <td width="138">(D,2)</td>

  </tr>

 </tbody>

</table>

The <strong>kmax </strong>method.

This method selects the <em>k<sup>th </sup></em>maximum value from a given collection, as defined by a given comparator. A value is the <em>k<sup>th </sup></em>maximum if there are exactly <em>k </em>−1 values greater than it in the collection. If either the collection or comparator is null, this method throws an IllegalArgumentException. If the collection is empty or if there is no <em>k<sup>th </sup></em>minimum value, this method throws a NoSuchElementException. Note that there is no <em>k<sup>th </sup></em>minimum value if <em>k </em>is less than 1, <em>k </em>is greater than the number of elements in the collection, or if <em>k </em>is greater than the number of distinct values in the collection. The collection must not be changed by this method.

<em>Examples:</em>

<table width="656">

 <tbody>

  <tr>

   <td width="118">T</td>

   <td width="212">c</td>

   <td width="23">k</td>

   <td width="162">comp</td>

   <td width="140">&lt;T&gt;kmax(c, k, comp)</td>

  </tr>

  <tr>

   <td width="118">Integer</td>

   <td width="212">[2, 8, 7, 3, 4]</td>

   <td width="23">1</td>

   <td width="162"><em>ascending order</em></td>

   <td width="140">8</td>

  </tr>

  <tr>

   <td width="118">Integer</td>

   <td width="212">[5, 9, 1, 7, 3]</td>

   <td width="23">2</td>

   <td width="162"><em>descending order</em></td>

   <td width="140">3</td>

  </tr>

  <tr>

   <td width="118">Integer</td>

   <td width="212">[8, 7, 6, 5, 4]</td>

   <td width="23">3</td>

   <td width="162"><em>ascending order</em></td>

   <td width="140">6</td>

  </tr>

  <tr>

   <td width="118">(String, Integer)</td>

   <td width="212">[(A,5), (B,4), (C,3), (D,2), (E, 1)]</td>

   <td width="23">4</td>

   <td width="162"><em>ascending by String field</em></td>

   <td width="140">(B,4)</td>

  </tr>

  <tr>

   <td width="118">(String, Integer)</td>

   <td width="212">[(A,5), (B,4), (C,3), (D,2), (E, 1)]</td>

   <td width="23">2</td>

   <td width="162"><em>ascending by Integer field</em></td>

   <td width="140">(B,4)</td>

  </tr>

 </tbody>

</table>

The <strong>range </strong>method.

This method returns a collection of all values <em>i </em>from a given collection such that <em>low </em>≤ <em>i </em>≤ <em>high</em>, as defined by the given comparator, including duplicate values. (Note that <em>low </em>and <em>high </em>do not have to be actual values in the given collection.) The returned collection contains only values in the range [low..high], and no others. If there are no qualifying values, including the case where c is empty, this method throws a NoSuchElementException. This method throws an IllegalArgumentException if either the collection or comparator is null. The collection is not changed by this method.

<em>Examples:</em>

<table width="659">

 <tbody>

  <tr>

   <td width="118">T</td>

   <td width="130">c</td>

   <td width="46">low</td>

   <td width="47">high</td>

   <td width="131">comp</td>

   <td width="186">&lt;T&gt;range(c, low, high, comp)</td>

  </tr>

  <tr>

   <td width="118">Integer</td>

   <td width="130">[2, 8, 7, 3, 4]</td>

   <td width="46">1</td>

   <td width="47">5</td>

   <td width="131"><em>ascending order</em></td>

   <td width="186">[2,3,4]</td>

  </tr>

  <tr>

   <td width="118">Integer</td>

   <td width="130">[5, 9, 1, 7, 3]</td>

   <td width="46">3</td>

   <td width="47">5</td>

   <td width="131"><em>ascending order</em></td>

   <td width="186">[5,3]</td>

  </tr>

  <tr>

   <td width="118">Integer</td>

   <td width="130">[5, 9, 1, 7, 3]</td>

   <td width="46">5</td>

   <td width="47">3</td>

   <td width="131"><em>descending order</em></td>

   <td width="186">[5,3]</td>

  </tr>

  <tr>

   <td width="118">Integer</td>

   <td width="130">[8, 7, 6, 5, 4]</td>

   <td width="46">4</td>

   <td width="47">8</td>

   <td width="131"><em>ascending order</em></td>

   <td width="186">[8, 7, 6, 5, 4]</td>

  </tr>

  <tr>

   <td width="118">(String, Integer)</td>

   <td width="130">[(A,5), (B,4), (C,3)]</td>

   <td width="46">(B,3)</td>

   <td width="47">(C,5)</td>

   <td width="131"><em>asc. by String field</em></td>

   <td width="186">[(B,4),(C,3)]</td>

  </tr>

  <tr>

   <td width="118">(String, Integer)</td>

   <td width="130">[(A,5), (B,4), (C,3)]</td>

   <td width="46">(F,4)</td>

   <td width="47">(G,7)</td>

   <td width="131"><em>asc. by Integer field</em></td>

   <td width="186">[(A,5),(B,4)]</td>

  </tr>

 </tbody>

</table>

The <strong>ceiling </strong>method.

This method returns the smallest value <em>i </em>in a given collection such that <em>i </em>≥ <em>key</em>, as defined by the given comparator. (Note that <em>key </em>does not have to be an actual value in the given collection.) If the given collection or comparator is null, this method throws an IllegalArgumentException. If the collection is empty or if there is no qualifying value <em>i</em>, this method throws a NoSuchElementException.

<em>Examples:</em>

<table width="695">

 <tbody>

  <tr>

   <td width="118">T</td>

   <td width="212">c</td>

   <td width="46">key</td>

   <td width="162">comp</td>

   <td width="157">&lt;T&gt;ceiling(c, key, comp)</td>

  </tr>

  <tr>

   <td width="118">Integer</td>

   <td width="212">[2, 8, 7, 3, 4]</td>

   <td width="46">1</td>

   <td width="162"><em>ascending order</em></td>

   <td width="157">2</td>

  </tr>

  <tr>

   <td width="118">Integer</td>

   <td width="212">[5, 9, 1, 7, 3]</td>

   <td width="46">7</td>

   <td width="162"><em>descending order</em></td>

   <td width="157">7</td>

  </tr>

  <tr>

   <td width="118">Integer</td>

   <td width="212">[8, 7, 6, 5, 4]</td>

   <td width="46">0</td>

   <td width="162"><em>ascending order</em></td>

   <td width="157">4</td>

  </tr>

  <tr>

   <td width="118">(String, Integer)</td>

   <td width="212">[(A,5), (B,4), (C,3), (D,2), (E, 1)]</td>

   <td width="46">(B,9)</td>

   <td width="162"><em>ascending by String field</em></td>

   <td width="157">(B,4)</td>

  </tr>

  <tr>

   <td width="118">(String, Integer)</td>

   <td width="212">[(A,5), (B,4), (C,3), (D,2), (E, 1)]</td>

   <td width="46">(F,0)</td>

   <td width="162"><em>ascending by Integer field</em></td>

   <td width="157">(E,1)</td>

  </tr>

 </tbody>

</table>

The <strong>floor </strong>method.

This method returns the largest value <em>i </em>in a given collection such that <em>i </em>≤ <em>key</em>, as defined by the given comparator. (Note that <em>key </em>does not have to be an actual value in the given collection.) If the given collection or comparator is null, this method throws an IllegalArgumentException. If the collection is empty or if there is no qualifying value <em>i</em>, this method throws a NoSuchElementException.

<em>Examples:</em>

<table width="685">

 <tbody>

  <tr>

   <td width="118">T</td>

   <td width="212">c</td>

   <td width="46">key</td>

   <td width="162">comp</td>

   <td width="146">&lt;T&gt;floor(c, key, comp)</td>

  </tr>

  <tr>

   <td width="118">Integer</td>

   <td width="212">[2, 8, 7, 3, 4]</td>

   <td width="46">6</td>

   <td width="162"><em>ascending order</em></td>

   <td width="146">4</td>

  </tr>

  <tr>

   <td width="118">Integer</td>

   <td width="212">[5, 9, 1, 7, 3]</td>

   <td width="46">1</td>

   <td width="162"><em>descending order</em></td>

   <td width="146">1</td>

  </tr>

  <tr>

   <td width="118">Integer</td>

   <td width="212">[8, 7, 6, 5, 4]</td>

   <td width="46">9</td>

   <td width="162"><em>ascending order</em></td>

   <td width="146">8</td>

  </tr>

  <tr>

   <td width="118">(String, Integer)</td>

   <td width="212">[(A,5), (B,4), (C,3), (D,2), (E, 1)]</td>

   <td width="46">(F,0)</td>

   <td width="162"><em>ascending by String field</em></td>

   <td width="146">(E,1)</td>

  </tr>

  <tr>

   <td width="118">(String, Integer)</td>

   <td width="212">[(A,5), (B,4), (C,3), (D,2), (E, 1)]</td>

   <td width="46">(B,9)</td>

   <td width="162"><em>ascending by Integer field</em></td>

   <td width="146">(A,5)</td>

  </tr>

 </tbody>

</table>

<h2>Notes and other requirements</h2>

Here are other specific requirements, notes, and suggestions.

<ul>

 <li>Read this handout carefully. Read the provided source code carefully. Ask questions on Piazza. Start early and be proactive.</li>

 <li>The constructor has been completed for you and must not be changed in any way.</li>

 <li>You may add any number of private methods that you like, but you may not add any public method or constructor, nor may you change the signature of any public method or constructor.</li>

 <li>You must not add any fields, either public or private, to the Selector class.</li>

 <li>You must not add any import statements to those already in the Selector class.</li>

 <li>You may not change or delete any import statement in the Selector class.</li>

 <li>You may not use fully-qualified names to circumvent the restrictions on imports above, except in the one instance noted below.</li>

 <li>None of the methods in the Selector class can modify the Collection parameter in any way. More generally, the methods in the Selector class should have no side-effects.</li>

 <li>You are only allowed to use sorting as part of your solution to kmin and kmax. You are not required to use sorting, but you are allowed to do so for these two methods only. If you use sorting, you must do so by calling the java.util.Collections.sort(List, Comparator) method. You must use the fully-qualified name (no importing Collections) and you are allowed at most two calls to this method – at most one in kmin and at most one in kmax.</li>

 <li>The use of the ArrayList class is allowed only in kmin, kmax, and range. No other method is allowed to use any implementing class of Collection.</li>

 <li>The declaration or use of an array in any method is strictly prohibited.</li>

 <li>Your code must be type safe; that is, your code must compile cleanly with no compiler warnings.</li>

</ul>