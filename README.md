# chapter-no-5
5.1 State whether the following are true or false. If the answer is false, explain why.
a) The default case is required in the switch selection statement.
False .The default case is optional. Nevertheless, it’s considered good software engineering to always provide a default case. 
b) The break statement is required in the default case of a switch selection statement to exit the switch properly.
False. The break statement is used to exit the switch statement. The break statement is not required when the default case is the last case. Nor will the break statement be required if having control proceed with the next case makes sense.
c) The expression (x > y && a<b) is true if either the expression x > y is true or the expression a<b is true. 
 False. When using the && operator, both of the relational expressions must be true for the entire expression to be true.
d) An expression containing the || operator is true if either or both of its operands are true.
 True
5.2 Write a C++ statement or a set of C++ statements to accomplish each of the following:
a) Sum the odd integers between 1 and 99 using a for statement. Assume the integer variables sum and count have been declared.
sum =0;
for  (count=1; count <= 99; count+=2)
sum+= count;
b) Print the integers from 1 to 20 using a while loop and the counter variable x. Assume that the variable x has been declared, but not initialized. Print only 5 integers per line. Hint: When x% 5 is 0, print a newline character; otherwise, print a tab character.]
 x=1;
while (x<=20)
{
if (x%5==0 )
cout << x << endl;
 else
 cout << x << "\t"; 
x++;}
c) Repeat Exercise 5.2(b) using a for statement.
 for (x=1; x<= 20; x++)
{
if (x %5==0) 
cout << x << endl;
 else
 cout <<x<<"\t";
}
5.3 Find the errors in each of the following code segments and explain how to correct them,

a) x=1;
while (x <=10);
 X++;
}
Error: The semicolon after the while header causes an infinite loop.
Correction: Replace the semicolon by a (, or remove both the; and the}.
b) for (y=.1; y !=1.0; y+=.1)
cout << y << endl;
Error: Using a floating-point number to control a for repetition statement.
Correction: Use an int and perform the proper calculation to get the values you desire.
 for (y=1; у!=10; у++)
cout << (static _cast< double> (y) /10) << endl;
c) switch (n)
case 1:
cout << "The number is 1” <<< endl;
case 2:
cout << "The number is 2 << endl;
break;
default:
cout << "The number is not 1 or 2 endl;
break;
Error: Missing break statement in the first case.
Correction: Add a break statement at the end of the first case. This is not an error if you want the statement of case 2: to execute every time the case 1: statement executes.
d) The following code should print the values 1 to 10.
n=1;
while (n<10)
cout<< n++ <<< endl;
Error: Improper relational operator used in the loop-continuation condition.
Correction: Use<= rather than<, or change 10 to 11.
5.4 Find the error(s), if any, in each of the following:
a) For (x =100, x>=1, x++)
cout << x << endl;
Errors:
For must be lowercase → for
Commas , should be semicolons ;
Logic error: x++ increases x, so x >= 1 will never stop (infinite loop)
Correct version (counting down):
for (x = 100; x >= 1; x--)
   cout << x << endl;
b) The following code should print whether integer value is odd or even:
switch (value %2){
case 0:
cout << "Even integer" << endl;
case 1:
 cout << "Odd integer" << endl;
}
Errors:
Missing break; statements → causes fall-through
Correct version:
switch (value % 2) {
case 0:
    cout << "Even integer" << endl;
    break;
case 1:
    cout << "Odd integer" << endl;
    break;
}
c) The following code should output the odd integers from 19 to 1:
for (x=19; x> = 1; x+=2)
cout<<x<<end1;
Errors:
x += 2 increases instead of decreases
end1 should be endl
Extra space in x> = 1
Correct version:
for (x = 19; x >= 1; x -= 2)
    cout << x << endl;
d) The following code should output the even integers from 2 to 100:
counter = 2;
do{
cout << counter<<end1;
 counter + =2;
} While (counter < 100);
Errors:
end1 → endl
counter + =2 → counter += 2
While should be lowercase → while
Condition should allow printing 100
Correct version:
counter = 2;
do {
    cout << counter << endl;
    counter += 2;
} while (counter <= 100);


5.5 (Summing Integers) Write a program that uses a for statement to sum a sequence of integers. Assume that the first integer read specifies the number of values remaining to be entered. Your program should read only one value per input statement. A typical input sequence might be
5 100 200 300 400 500
where the 5 indicates that the subsequent 5 values are to be summed.
Summing Integers
Program:
#include <iostream>
using namespace std;
int main() {
    int count, value, sum = 0;
    cin >> count;   // number of values to read
    for (int i = 1; i <= count; i++) {
        cin >> value;
        sum += value;
    }
    cout << "Sum = " << sum << endl;
    return 0;
}
5.6 (Averaging Integers) Write a program that uses a for statement to calculate the average of several integers. Assume the last value read is the sentinel 9999. A typical input sequence might be 10 8 11 7 9 9999
indicating that the program should calculate the average of all the values preceding 9999.
 Averaging Integers (sentinel = 9999)
#include <iostream>
using namespace std;
int main() {
    int value, sum = 0, count = 0;
    cin >> value;
    for (; value != 9999; ) {
        sum += value;
        count++;
        cin >> value;
    if (count != 0)
        cout << "Average = " << static_cast<double>(sum) / count << endl;
    return 0;
}
5.7 What does the following program do?
#include <iostream>
using namespace std;
int main()
{
int x; // declare x
int y: // declare y
//prompt user for input
cout << "Enter two integers in the range 1-20: ";
cin >> x >> y; // read values for x and y
for (int i=1; i<= y; i++) // count from 1 to y
{
for (int j=1;j<= x; j++) // count from 1 to x
cout <<’@’; // output @
cout << endl; // begin new line
}// end outer for
} // end main
First, there’s a syntax error
int y:
Should be:
int y;
What the program does
Reads two integers x and y (between 1 and 20)
Prints a rectangle of @ symbols
x = number of @ per row
y = number of rows
Example
Input:
5 3
Output:
@@@@@
@@@@@
@@@@@
5.8 (Find the Smallest Integer) Write a program that uses a for statement to find the smallest of several integers. Assume that the first value read specifies the number of values remaining.
Program:
#include <iostream>
using namespace std;
int main() {
    int n, value, smallest;
    cin >> n;          // number of values
    cin >> smallest;   // read first value
    for (int i = 1; i < n; i++) {
        cin >> value;
        if (value < smallest)
            smallest = value;
    }
    cout << "Smallest = " << smallest << endl;
    return 0;
}
5.9 (Product of Odd Integers) Write a program that uses a for statement to calculate and print the product of the odd integers from 1 to 15.
Program:
#include <iostream>
using namespace std;
int main() {
    int product = 1;
    for (int i = 1; i <= 15; i += 2) {
        product *= i;
    }
    cout << "Product = " << product << endl;
    return 0;
}
What is the program of this output:
a)                                                            b)                                                                          c)
*                                                            **********                                                      **********
**                                                          *********                                                          *********
***                                                        ********                                                              ********
****                                                      *******                                                                  *******
*****                                                    ******                                                                      ******
******                                                  *****                                                                          *****      
*******                                                ****                                                                              ****
********                                              ***                                                                                  ***
*********                                            **                                                                                      **
**********                                          *                                                                                          *

d)
                  *
                **
              ***
            ****
          *****
        ******
      *******
    ********
  *********
**********
                                                                
   C++ Program                    
#include <iostream>
using namespace std;
int main() {
 for (int i = 10; i >= 1; i--) {
for (int j = 1; j <= i; j++) {
cout << "*";
}
cout << endl;
}
return 0;
}
Output
**********
*********
********
*******
******
*****
****
***
**
*
Program
#include <iostream>
using namespace std;
int main() {
  for (int i = 10; i >= 1; i--) {
// print leading spaces
for (int space = 0; space < 10 - i; space++) {
cout << " "; }
// print stars
for (int star = 1; star <= i; star++) {
  cout << "*";
  }
   cout << endl;
    }
    return 0;
}
Output
**********
 *********
  ********
   *******
    ******
     *****
      ****
       ***
        **
         *
Program
#include <iostream>
 using namespace std; 
int main()
 { for (int i = 1; i <= 10; i++)
 { for (int j = 1; j <= i; j++) 
{ cout << "*"; } cout << endl; } 
return 0; }  
output :
*
**
***
****
*****
******
*******
********
*********
**********   
 Program
#include <iostream>
using namespace std;

int main() {
for (int i = 1; i <= 10; i++) {
// print leading spaces
for (int space = 1; space <= 10 - i; space++) {
cout << "  ";
}  // print stars
for (int star = 1; star <= i; star++) {
cout << "*";
  }
cout << endl;
}
return 0;
}
Output
                  *
                **
              ***
            ****
          *****
        ******
      *******
    ********
  *********
**********
  5.17 (What Prints?) Assume i = 1, j = 2, k = 3 and m = 2. What does each statement print?
Given:i = 1, j = 2, k = 3, m = 2
In ++, true prints as 1 and false prints as 0.
a) cout << (i==1)<<endl;
1 == 1 → true
Output: 1
b) cout << (j ==3) << endl;
 2 == 3 → false
  Output: 0
c) cout << (i >= 1 && j < 4 ) << endl;
 i >= 1 → 1 >= 1 → true
 j < 4 → 2 < 4 → true
 true && true → true
Output: 1
d) cout << (m <= 99 && k<m) << endl;
m <= 99 → 2 <= 99 → true
k < m → 3 < 2 → false
true && false → false
Output: 0
e) cout << (j>=i || k == m ) << endl;
j >= i → 2 >= 1 → true
k == m → 3 == 2 → false
true || false → true
Output: 1
f) cout << (k+m<j || 3- j >= k ) << endl;
k + m < j → 3 + 2 < 2 → 5 < 2 → false
3 - j >= k → 3 - 2 >= 3 → 1 >= 3 → false
false || false → false
Output: 0
g) cout << (!m) << endl;
m = 2 (non-zero → true)
!true → false
Output: 0
h) cout << (!(j-m)) << endl;
j - m → 2 - 2 = 0
0 → false
!false → true
Output: 1
i) cout << (!(k>m)) << endl;
k > m → 3 > 2 → true
!true → false
Output: 0
5.22 Solutions
a)
Original:
!(x < 5) && !(y >= 7)
This is already negated individually.Rewrite as a single negation using De Morgan:
Equivalent expression:
!((x < 5) || (y >= 7))
b)
Original:
!(a == b) || !(g != 5)
Apply De Morgan in reverse:
Equivalent expression:
!((a == b) && (g != 5))
c)
Original:
!((x <= 8) && (y > 4))
Apply De Morgan directly:
Equivalent expression:
(x > 8) || (y <= 4)
d)
Original:
!((i > 4) || (j <= 6))
Apply De Morgan directly:
Equivalent expression:
(i <= 4) && (j > 6)
Program to Demonstrate Equivalence
#include <iostream>
using namespace std;

int main() {
    int x = 4, y = 6, a = 3, b = 5, g = 5, i = 3, j = 7;

    cout << "a) "
         << ( !(x < 5) && !(y >= 7) ) << "  "
         << ( !((x < 5) || (y >= 7)) ) << endl;

    cout << "b) "
         << ( !(a == b) || !(g != 5) ) << "  "
         << ( !((a == b) && (g != 5)) ) << endl;

    cout << "c) "
         << ( !((x <= 8) && (y > 4)) ) << "  "
         << ( (x > 8) || (y <= 4) ) << endl;

    cout << "d) "
         << ( !((i > 4) || (j <= 6)) ) << "  "
         << ( (i <= 4) && (j > 6) ) << endl;

    return 0;
}
5.23 (Diamond of Asterisks) Write a program that prints the following diamond shape. You may use output statements that print a single asterisk (*), a single blank or a single newline. Maximize your use of repetition (with nested for statements) and minimize the number of output statements.
Program: Diamond of Asterisks
#include <iostream>
using namespace std;
int main() {
int n = 5;   // half height of diamond
    // upper half (including middle)
for (int i = 1; i <= n; i++) {
for (int space = 1; space <= n - i; space++)
cout << " ";
for (int star = 1; star <= 2 * i - 1; star++)
cout << "*";
cout << endl;
 }
// lower half
 for (int i = n - 1; i >= 1; i--) {
for (int space = 1; space <= n - i; space++)
cout << " ";
for (int star = 1; star <= 2 * i - 1; star++)
cout << "*";
cout << endl;
 }
return 0;
}
Output
         *
       ***
    *****
  *******
*********
  *******
    *****
      ***
        *
5.26 What does the following program segment do?
Program:
for (int i = 1; i <= 5; i++)
{
for (int j = 1; j <= 3; j++)
{
for (int k = 1; k <= 4; k++)
cout << '*';
cout << endl;
} // end inner for
cout << endl;
} // end outer for
Output :
****
****
****

****
****
****

****
****
****

****
****
****

****
****
****
