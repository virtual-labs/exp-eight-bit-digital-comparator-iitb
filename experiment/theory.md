
#### Introduction:

The outcome of comparison between two numbers takes any of the three possibilities:
Either both the numbers A & B are equal (A = B), or number A is greater than number B (A &gt; B) or number A is smaller than number B (A &lt; B).
Any byte consists of two nibbles (lower nibble and the upper nibble) i.e. 8 bits. To compare two – 8 bit numbers, the concept used is to compare the most significant bits (MSB’s) of the two numbers and proceed with the next bit.

#### IC 7485 Based 8 bit Comparator:
IC 7485 is a 4-bit comparator with two – 4 bit inputs and three cascade inputs and three compare outputs, A < B, A = B and A > B. The cascade inputs enable cascading of multiple ICs 7485 to obtain N- magnitude comparator (N is an integer). To compare two 8-bit numbers two such ICs are required. IC 7485 can be expanded to compare more than 4 bit numbers. An 8-bit comparator compares the two 8-bit numbers by cascading of two 4-bit comparator ICs 7485. 

#### Connection Diagram:
<ol>
<li>
For the lower order comparator IC 7485 (1), the A=B cascade input must be connected to Logic 1 (Vcc), while the other two cascade inputs must be connected to Logic 0 (ground).
</li>
<li>
The lower order comparator outputs, A < B, A = B and A > B are connected to the respective cascade inputs of the higher order comparator IC 7485(2).
</li>
<li>
The outputs of the higher order comparator become the final outputs of this eight-bit comparator.
</li>
Fig.1 shows the connection diagram for 8 bit comparator using multiple 7485 ICs.
</ol>

<center>
<img src="images/image005.png"><br/>
<p>Fig 1. Eight bit Magnitude Comparator</p>
</center>

<b> Note: </b><br/>
<b>8 bit Input A:</b>  A7 &nbsp; A6 &nbsp; A5 &nbsp; A4 &nbsp; A3 &nbsp; A2 &nbsp; A1 &nbsp; A0 <br/>
<b>8 bit Input B:</b> B7 &nbsp; B6 &nbsp; B5 &nbsp; B4 &nbsp; B3 &nbsp; B2 &nbsp; B1 &nbsp; B0 <br/>
Where A7 & B7 are the MSBs of binary numbers A & B respectively.<br/>


The Comparator compare the number bit by bit from MSB to LSB.

The function table of 8-bit comparator is:
<table>
 <tr>
  <th colspan=8>Comparing Input</th>
  <th colspan=3>Output</th>
 </tr>
 <tr>
  <th>A<sub>7</sub>,B<sub>7</sub> </th>
  <th>A<sub>6</sub>,B<sub>6</sub></th>
  <th>A<sub>5</sub>,B<sub>5</sub></th>
  <th>A<sub>4</sub>,B<sub>4</sub></th>
  <th>A<sub>3</sub>,B<sub>3</sub> </th>
  <th>A<sub>2</sub>,B<sub>2</sub></th>
  <th>A<sub>1</sub>,B<sub>1</sub></th>
  <th>A<sub>0</sub>,B<sub>0</sub></th>
  <th>A &gt; B</th>
  <th>A = B</th>
  <th>A &lt; B</th>
 </tr>
 <tr>
  <td>A<sub>7</sub>  &gt; B<sub>7</sub></td>
  <td>X</td>
  <td>X</td>
  <td>X</td>
  <td>X</td>
  <td>X</td>
  <td>X</td>
  <td>X</td>
  <td>1</td>
  <td>0</td>
  <td>0</td>
 </tr>
 <tr>
  <td>A<sub>7</sub>&lt; B<sub>7</sub></td>
  <td>X</td>
  <td>X</td>
  <td>X</td>
  <td>X</td>
  <td>X</td>
  <td>X</td>
  <td>X</td>
  <td>0</td>
  <td>0</td>
  <td>1</td>
 </tr>
 <tr>
  <td>A<sub>3</sub> = B<sub>7</sub></td>
  <td>A<sub>6</sub>&gt; B<sub>6</sub></td>
  <td>X</td>
  <td>X</td>
  <td>X</td>
  <td>X</td>
  <td>X</td>
  <td>X</td>
  <td>1</td>
  <td>0</td>
  <td>0</td>
 </tr>
 <tr>
  <td>A<sub>7</sub>= B<sub>7</sub></td>
  <td>A<sub>6</sub>&lt; B<sub>6</sub></td>
  <td>X</td>
  <td>X</td>
  <td>X</td>
  <td>X</td>
  <td>X</td>
  <td>X</td>
  <td>0</td>
  <td>0</td>
  <td>1</td>
 </tr>
 <tr>
  <td>A<sub>7</sub>= B<sub>7</sub></td>
  <td>A<sub>6</sub>= B<sub>6</sub></td>
  <td>A<sub>5</sub>&gt; B<sub>5</sub></td>
  <td>X</td>
  <td>X</td>
  <td>X</td>
  <td>X</td>
  <td>X</td>
  <td>1</td>
  <td>0</td>
  <td>0</td>
 </tr>
 <tr>
  <td>A<sub>7</sub>= B<sub>7</sub></td>
  <td>A<sub>6</sub>= B<sub>6</sub></td>
  <td>A<sub>5</sub>&lt; B<sub>5</sub></td>
  <td>X</td>
  <td>X</td>
  <td>X</td>
  <td>X</td>
  <td>X</td>
  <td>0</td>
  <td>0</td>
  <td>1</td>
 </tr>
 <tr>
  <td>A<sub>7</sub>= B<sub>7</sub></td>
  <td>A<sub>6</sub>= B<sub>2</sub></td>
  <td>A<sub>5</sub>= B<sub>5</sub></td>
  <td>A<sub>4</sub>&gt; B<sub>4</sub></td>
  <td>X</td>
  <td>X</td>
  <td>X</td>
  <td>X</td>
  <td>1</td>
  <td>0</td>
  <td>0</td>
 </tr>
 <tr>
  <td>A<sub>7</sub>= B<sub>7</sub></td>
  <td>A<sub>6</sub>= B<sub>6</sub></td>
  <td>A<sub>5</sub>= B<sub>5</sub></td>
  <td>A<sub>4</sub>&lt; B<sub>4</sub></td>
  <td>X</td>
  <td>X</td>
  <td>X</td>
  <td>X</td>
  <td>0</td>
  <td>0</td>
  <td>1</td>
 </tr>
 <tr>
  <td>A<sub>7</sub>= B<sub>7</sub></td>
  <td>A<sub>6</sub>= B<sub>6</sub></td>
  <td>A<sub>5</sub>= B<sub>5</sub></td>
  <td>A<sub>4</sub>= B<sub>4</sub></td>
  <td>A<sub>3</sub>&gt; B<sub>3</sub></td>
  <td>X</td>
  <td>X</td>
  <td>X</td>
  <td>1</td>
  <td>0</td>
  <td>0</td>
 </tr>
 <tr>
  <td>A<sub>7</sub>= B<sub>7</sub></td>
  <td>A<sub>6</sub>= B<sub>6</sub></td>
  <td>A<sub>5</sub>= B<sub>5</sub></td>
  <td>A<sub>4</sub>= B<sub>4</sub></td>
  <td>A<sub>3</sub>&lt; B<sub>3</sub></td>
  <td>X</td>
  <td>X</td>
  <td>X</td>
  <td>0</td>
  <td>0</td>
  <td>1</td>
 </tr>
 <tr>
  <td>A<sub>7</sub>= B<sub>7</sub></td>
  <td>A<sub>6</sub>= B<sub>6</sub></td>
  <td>A<sub>5</sub>= B<sub>5</sub></td>
  <td>A<sub>4</sub>= B<sub>4</sub></td>
  <td>A<sub>3</sub>= B<sub>3</sub></td>
  <td>A<sub>2</sub>&gt; B<sub>2</sub></td>
  <td>X</td>
  <td>X</td>
  <td>1</td>
  <td>0</td>
  <td>0</td>
 </tr>
 <tr>
  <td>A<sub>7</sub>= B<sub>7</sub></td>
  <td>A<sub>6</sub>= B<sub>6</sub></td>
  <td>A<sub>5</sub>= B<sub>5</sub></td>
  <td>A<sub>4</sub>= B<sub>4</sub></td>
  <td>A<sub>3</sub>= B<sub>3</sub></td>
  <td>A<sub>2</sub>&lt; B<sub>2</sub></td>
  <td>X</td>
  <td>X</td>
  <td>0</td>
  <td>0</td>
  <td>1</td>
 </tr>
 <tr>
  <td>A<sub>7</sub>= B<sub>7</sub></td>
  <td>A<sub>6</sub>= B<sub>6</sub></td>
  <td>A<sub>5</sub>= B<sub>5</sub></td>
  <td>A<sub>4</sub>= B<sub>4</sub></td>
  <td>A<sub>3</sub>= B<sub>3</sub></td>
  <td>A<sub>2</sub>= B<sub>2</sub></td>
  <td>A<sub>1</sub>&gt; B<sub>1</sub></td>
  <td>X</td>
  <td>1</td>
  <td>0</td>
  <td>0</td>
 </tr>
 <tr>
  <td>A<sub>7</sub>= B<sub>7</sub></td>
  <td>A<sub>6</sub>= B<sub>6</sub></td>
  <td>A<sub>5</sub>= B<sub>5</sub></td>
  <td>A<sub>4</sub>= B<sub>4</sub></td>
  <td>A<sub>3</sub>= B<sub>3</sub></td>
  <td>A<sub>2</sub>= B<sub>2</sub></td>
  <td>A<sub>1</sub>&lt; B<sub>1</sub></td>
  <td>X</td>
  <td>0</td>
  <td>0</td>
  <td>1</td>
 </tr>
 <tr>
  <td>A<sub>7</sub>= B<sub>7</sub></td>
  <td>A<sub>6</sub>= B<sub>6</sub></td>
  <td>A<sub>5</sub>= B<sub>5</sub></td>
  <td>A<sub>4</sub>= B<sub>4</sub></td>
  <td>A<sub>3</sub>= B<sub>3</sub></td>
  <td>A<sub>2</sub>= B<sub>2</sub></td>
  <td>A<sub>1</sub>= B<sub>1</sub></td>
  <td>A<sub>0</sub>&gt; B<sub>0</sub></td>
  <td>1</td>
  <td>0</td>
  <td>0</td>
 </tr>
 <tr>
  <td>A<sub>7</sub>= B<sub>7</sub></td>
  <td>A<sub>6</sub>= B<sub>6</sub></td>
  <td>A<sub>5</sub>= B<sub>5</sub></td>
  <td>A<sub>4</sub>= B<sub>4</sub></td>
  <td>A<sub>3</sub>= B<sub>3</sub></td>
  <td>A<sub>2</sub>= B<sub>2</sub></td>
  <td>A<sub>1</sub>= B<sub>1</sub></td>
  <td>A<sub>0</sub>&lt; B<sub>0</sub></td>
  <td>0</td>
  <td>0</td>
  <td>1</td>
 </tr>
 <tr>
  <td>A<sub>7</sub>= B<sub>7</sub></td>
  <td>A<sub>6</sub>= B<sub>6</sub></td>
  <td>A<sub>5</sub>= B<sub>5</sub></td>
  <td>A<sub>4</sub>= B<sub>4</sub></td>
  <td>A<sub>3</sub>= B<sub>3</sub></td>
  <td>A<sub>2</sub>= B<sub>2</sub></td>
  <td>A<sub>1</sub>= B<sub>1</sub></td>
  <td>A<sub>0</sub>= B<sub>0</sub></td>
  <td>0</td>
  <td>1</td>
  <td>0</td>
 </tr>
</table>

<br/><br/>

Example:
<ol>
<li>
	A = 0, B = 8
	<br>
	&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A = 0 (Decimal)&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 0000 0000 (Binary)<br>
	&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;B = 8 (Decimal)&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 0000 1000 (Binary)
	<br/>
	Ans:
	<br/>
	<table>
		<tr>
			<th>A&gt;B</th>
			<th>A=B</th>
			<th>A&lt;B</th>
		<tr>
		<tr>
			<td>Low</td>
			<td>Low</td>
			<td>High</td>
		<tr>
	</table>
	<br/><br/><br/>
</li>
<li>
	A = 64, B = 8
	<br>
	&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A = 64 (Decimal)&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 0100 0000 (Binary)<br>
	&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;B = &nbsp;&nbsp;8 (Decimal)&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 0000 1000 (Binary)
	<br/>
	Ans:
	<br/>
	<table>
		<tr>
			<th>A&gt;B</th>
			<th>A=B</th>
			<th>A&lt;B</th>
		<tr>
		<tr>
			<td>High</td>
			<td>Low</td>
			<td>Low</td>
		<tr>
	</table>
	<br/><br/><br/>
</li>
<li>
	A = 96, B = 96
	<br>
	&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A = 96 (Decimal)&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 0110 0000 (Binary)<br>
	&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;B = 96 (Decimal)&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 0110 0000 (Binary)
	<br/>
	Ans:
	<br/>
	<table>
		<tr>
			<th>A&gt;B</th>
			<th>A=B</th>
			<th>A&lt;B</th>
		<tr>
		<tr>
			<td>Low</td>
			<td>High</td>
			<td>Low</td>
		<tr>
	</table>
	<br/><br/><br/>
</li>
<li>
	A = 30, B = 23
	<br>
	&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A = 30 (Decimal)&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  0001 1110 (Binary)<br>
	&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;B = 23 (Decimal)&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 0001 10111 (Binary)
	<br/>
	Ans:
	<br/>
	<table>
		<tr>
			<th>A&gt;B</th>
			<th>A=B</th>
			<th>A&lt;B</th>
		<tr>
		<tr>
			<td>High</td>
			<td>Low</td>
			<td>Low</td>
		<tr>
	</table>
	<br/><br/><br/>
</li>
<li>
	A = 42, B = 42
	<br>
	&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A = 42 (Decimal)&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 00101010 (Binary)<br>
	&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;B = 42 (Decimal)&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 00101010 (Binary)
	<br/>
	Ans:
	<br/>
	<table>
		<tr>
			<th>A&gt;B</th>
			<th>A=B</th>
			<th>A&lt;B</th>
		<tr>
		<tr>
			<td>Low</td>
			<td>High</td>
			<td>Low</td>
		<tr>
	</table>
	<br/><br/><br/>
</li>
</ol>


</body>

</html>
<script type="text/javascript" id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"> </script>