# Lab-7_202001136
## IT314-Software Engineering Lab-7
### Testing

#### Section A:
Consider a program for determining the previous date. Its input is triple of day, month and year with the following ranges 1 <= month <= 12, 1 <= day <= 31, 1900 <= year <= 2015.
The possible output dates would be previous date or invalid date. Design the equivalence class test cases? Write a set of test cases (i.e., test suite) – specific set of data – to properly test the programs. Your test suite
should include both correct and incorrect inputs.
1. Enlist which set of test cases have been identified using Equivalence Partitioning and Boundary Value Analysis separately.
2. Modify your programs such that it runs on eclipse IDE, and then execute your test suites on the program. While executing your input data in a program, check whether the identified expected outcome (mentioned by you) is correct or not.

The solution of each problem must be given in the format as follows:

**Tester Action and Input Data&emsp;&emsp;&emsp;Expected Outcome**

##### Equivalence Partitioning </br>
&emsp;&emsp;a, b, c &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp; An Error message</br>
&emsp;&emsp;a-1, b, c     &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;   Yes</br>

##### Boundary Value Analysis</br>

&emsp;&emsp;a, b, c-1     &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;   Yes</br>

#### Programs:
**P1.** The function linearSearch searches for a value v in an array of integers a. If v appears in the array a, then the function returns the first index i, such that a[i] == v; otherwise, -1 is returned.</br>
int linearSearch(int v, int a[])</br>
{</br>
&emsp;&emsp;&emsp;int i = 0;</br>
&emsp;&emsp;&emsp;while (i < a.length)</br>
&emsp;&emsp;&emsp;{</br>
&emsp;&emsp;&emsp;&emsp;&emsp;if (a[i] == v)</br>
&emsp;&emsp;&emsp;&emsp;&emsp;return(i);</br>
&emsp;&emsp;&emsp;&emsp;&emsp;i++;</br>
&emsp;&emsp;&emsp;}</br>
&emsp;&emsp;&emsp;return (-1);</br>
}
</br></br>
**P2.** The function countItem returns the number of times a value v appears in an array of integers a.</br>
int countItem(int v, int a[])</br>
{</br>
&emsp;&emsp;&emsp;int count = 0;</br>
&emsp;&emsp;&emsp;for (int i = 0; i < a.length; i++)</br>
&emsp;&emsp;&emsp;{</br>
&emsp;&emsp;&emsp;&emsp;&emsp;if (a[i] == v)</br>
&emsp;&emsp;&emsp;&emsp;&emsp;count++;</br>
&emsp;&emsp;&emsp;}</br>
&emsp;&emsp;&emsp;return (count);</br>
}
</br></br>
**P3.** The function binarySearch searches for a value v in an ordered array of integers a. If v appears in the array a, then the function returns an index i, such that a[i] == v; otherwise, -1 is returned. Assumption: the elements in the array a are sorted in non-decreasing order.
int binarySearch(int v, int a[])</br>
{</br>
&emsp;&emsp;&emsp;int lo,mid,hi;</br>
&emsp;&emsp;&emsp;lo = 0;</br>
&emsp;&emsp;&emsp;hi = a.length-1;</br>
&emsp;&emsp;&emsp;while (lo <= hi)</br>
&emsp;&emsp;&emsp;{</br>
&emsp;&emsp;&emsp;&emsp;&emsp;mid = (lo+hi)/2;</br>
&emsp;&emsp;&emsp;&emsp;&emsp;if (v == a[mid])</br>
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;return (mid);</br>
&emsp;&emsp;&emsp;&emsp;&emsp;else if (v < a[mid])</br>
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;hi = mid-1;</br>
&emsp;&emsp;&emsp;&emsp;&emsp;else</br>
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;lo = mid+1;</br>
&emsp;&emsp;&emsp;}</br>
&emsp;&emsp;&emsp;return(-1);</br>
}
</br></br>
**P4.** The following problem has been adapted from The Art of Software Testing, by G. Myers (1979). The function triangle takes three integer parameters that are interpreted as the lengths of the sides of a triangle. It returns whether the triangle is equilateral (three lengths equal), isosceles (two lengths equal),
scalene (no lengths equal), or invalid (impossible lengths).
final int EQUILATERAL = 0;</br>
final int ISOSCELES = 1;</br>
final int SCALENE = 2;</br>
final int INVALID = 3;</br>
int triangle(int a, int b, int c)</br>
{</br>
&emsp;&emsp;&emsp;if (a >= b+c || b >= a+c || c >= a+b)</br>
&emsp;&emsp;&emsp;&emsp;&emsp;return(INVALID);</br>
&emsp;&emsp;&emsp;if (a == b && b == c)</br>
&emsp;&emsp;&emsp;&emsp;&emsp;return(EQUILATERAL);</br>
&emsp;&emsp;&emsp;if (a == b || a == c || b == c)</br>
&emsp;&emsp;&emsp;&emsp;&emsp;return(ISOSCELES);</br>
&emsp;&emsp;&emsp;return(SCALENE);</br>
}
</br></br>
**P5.** The function prefix (String s1, String s2) returns whether or not the string s1 is a prefix of string s2 (you may assume that neither s1 nor s2 is null).</br>
public static boolean prefix(String s1, String s2)</br>
{</br>
&emsp;&emsp;&emsp;if (s1.length() > s2.length())</br>
&emsp;&emsp;&emsp;{</br>
&emsp;&emsp;&emsp;&emsp;&emsp;return false;</br>
&emsp;&emsp;&emsp;}</br>
&emsp;&emsp;&emsp;for (int i = 0; i < s1.length(); i++)</br>
&emsp;&emsp;&emsp;{</br>
&emsp;&emsp;&emsp;&emsp;&emsp;if (s1.charAt(i) != s2.charAt(i))</br>
&emsp;&emsp;&emsp;&emsp;&emsp;{</br>
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;return false;</br>
&emsp;&emsp;&emsp;&emsp;&emsp;}</br>
&emsp;&emsp;&emsp;}</br>
&emsp;&emsp;&emsp;return true;</br>
}
</br></br>
**P6.** Consider again the triangle classification program (P4) with a slightly different specification: The program reads floating values from the standard input. The three values A, B, and C are interpreted as representing the lengths of the sides of a triangle. The program then prints a message to the standard output that states whether the triangle, if it can be formed, is scalene, isosceles, equilateral, or right angled. Determine the following for the above program:</br>
a) Identify the equivalence classes for the system.</br>
b) Identify test cases to cover the identified equivalence classes. Also, explicitly mention which test case would cover which equivalence class.</br>
(Hint: you must need to be ensure that the identified set of test cases cover all identified equivalence classes)</br>
c) For the boundary condition A + B > C case (scalene triangle), identify test cases to verify the boundary.</br>
d) For the boundary condition A = C case (isosceles triangle), identify test cases to verify the boundary.</br>
e) For the boundary condition A = B = C case (equilateral triangle), identify test cases to verify the boundary.</br>
f) For the boundary condition A<sup>2</sup> + B<sup>2</sup> = C<sup>2</sup> case (right-angle triangle), identify test cases to verify the boundary.</br>
g) For the non-triangle case, identify test cases to explore the boundary.</br>
h) For non-positive input, identify test points.</br>
</br>
**Lab Execution (how to perform the exercises):**
1. Write source code in eclipse IDE, write so obtained test cases in Junit testing framework and run the test cases.
