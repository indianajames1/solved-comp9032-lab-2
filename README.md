Download Link: https://assignmentchef.com/product/solved-comp9032-lab-2
<br>
<span style="font-size: 2.61792em; letter-spacing: -1px; font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen-Sans, Ubuntu, Cantarell, 'Helvetica Neue', sans-serif;">1.  Objectives</span>




In this lab, you will learn AVR programming on       memory access, and

    stack and function.







<h1>2.  Tasks</h1>




2.1 Task 1: String to Integer Conversion (Due Week 5)




The C program in Figure 1 <strong>implements the function</strong> of converting a string to an integer.

The string is given in main() and its integer is obtained by calling function atoi(). Manually translate the program into an assembly program <strong>with <em>atoi</em> implemented as a function.</strong> Assume the string is stored in the program memory and that an integer takes two bytes.




<table width="397">

 <tbody>

  <tr>

   <td width="397"><strong>int main(void) { char s[ ] = “12345”; int number; number = atoi(s);</strong><strong>return 0;</strong><strong>}</strong><strong>int atoi(char *a) {</strong><strong>char i; char c; int n;</strong><strong>n = 0; c = *a;</strong><strong>for (i=1; ((c &gt;=’0′) &amp;&amp; (c&lt;=’9′) &amp;&amp; (n&lt;65536)); i++){</strong><strong>n = 10 * n + (c -‘0’); c = *(a+i);</strong><strong>}</strong><strong>return n;</strong><strong>}</strong></td>

  </tr>

 </tbody>

</table>




<h2>Figure 1  string_to_number.c</h2>







2.2  Task 2:  Positional Division (Due Week 6)




Hand-division is a positional division that uses a series of left shifts, magnitude checks and multiple subtractions to get the result. The program in Figure 2 describes the positional division algorithm for the 16-bit <strong>binary division</strong>. Manually translate the program into an assembly function. Assume the dividend and the divisor are stored in the program memory and that the quotient is saved in the data memory. To test your design, you need to create a caller to the function.




<table width="392">

 <tbody>

  <tr>

   <td width="392"><strong>int posdiv(unsigned int dividend, unsigned int divisor) {</strong><strong>unsigned int quotient; unsigned int bit_position = 1; quotient = 0;</strong><strong>while ((dividend &gt; divisor) &amp;&amp; !(divisor &amp; 0x8000)) {</strong><strong>divisor = divisor &lt;&lt; 1;</strong><strong>bit_position = bit_position &lt;&lt; 1;</strong><strong>}</strong><strong>while (bit_position &gt; 0) { if (dividend &gt;= divisor) { dividend = dividend – divisor; quotient = quotient + bit_position;</strong><strong>}</strong><strong>divisor = divisor &gt;&gt; 1;</strong><strong>bit_position = bit_position &gt;&gt; 1;</strong><strong>}</strong><strong>return quotient; }</strong></td>

  </tr>

 </tbody>

</table>




<h2>Figure 2:  binary_positional_division.c</h2>







Note: Each task is worth 6 marks. All your programs should <u>be well commented</u> <u>and easy to read</u>. Up to 1 mark will be deducted for each program without proper and sufficient comments.