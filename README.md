# Lab-7_202001136
## IT314-Software Engineering Lab-7
### Testing

#### Section A:
Consider a program for determining the previous date. Its input is triple of day, month and year with the following ranges 1 <= month <= 12, 1 <= day <= 31, 1900 <= year <= 2015.
The possible output dates would be previous date or invalid date. 


Design the equivalence class test cases? 

<pre>
The equivalence classes obtained are as follows:
EC1 -> date>=1 and date<=31
EC2 -> date<1
EC3 -> date>31
EC4 -> month>=1 amd month<=12
EC5 -> month<1
EC6 -> month>12
EC7 -> year>=1900 and year<=2015
EC8 -> year<1900 
EC9 -> year>2015
</pre>

<pre>
Some of the equivalent test cases are as follows:
EC1 -> day = 5, month = 10, year = 2010, output = 4/10/2010
EC2 -> day = 0, month = 11, year = 1999, output = invalid date
EC3 -> day = 32, month = 3, year = 2008, output = invalid date
EC4 -> day = 1, month = 7, year = 1987, output = 30/06/1987
EC5 -> day = 13, month = 0, year = 1974, output = invalid date
EC6 -> date = 20, month = 14, year = 2013, output = invalid date
EC7 -> date = 4, month = 8, year = 2011, output = 3/08/2011
EC8 -> date = 8, month = 9, year = 1899, output = invalid date
EC9 -> date = 23, month = 2, year = 2016, output = invlid date
</pre>

<pre>
Valid dates - calculate previous dates:

1. 4/08/2011
output - 3/08/2011

2. 13/12/2012
output - 12/12/2012
</pre>

<pre>
Invalid dates: 

1. 0/11/1999
2. 20/12/2013
</pre>

<pre>
Dates having out of range values:

1. 8/9/1899
2. 23/2/2016
</pre>
<pre>
Boundary Value Analysis

1. Earliest date according to given range - 1/1/1900
2. Last possible date according to given range - 31/12/2015
3. Previous day of earliest date according to given range - 31/12/1899
4. Day after latest date according to given range - 1/1/2016
5. Leap year - 29-2-2004
6. Invalid leap year - 29-2-2013
</pre>

Write a set of test cases (i.e., test suite) – specific set of data – to properly test the programs. Your test suite should include both correct and incorrect inputs.
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


<pre>
Java code:
package Lab7_1;

public class Lab7_1_class {
	public static int linearSearch(int v, int[] a) 
	{
	    int i = 0;
	    while (i < a.length) {
	        if (a[i] == v) {
	            return i;
	        }
	        i++;
	    }
	    return -1;
	}
}
</pre>

<pre>
Equivalence Partitioning 
Tester Action and Input Data          Expected Outcome
&emsp;&emsp;v = 3, a = {3,7,4}                          0
&emsp;&emsp;v = 8, a = {3,7,4}                         -1
&emsp;&emsp;v = 4, a = {3,7,4}                          2
</pre>

<pre>
Boundary Value Analysis
Tester Action and Input Data          Expected Outcome
&emsp;&emsp;v = 3, a = {}                              -1
&emsp;&emsp;v = 0, a = {3,7,4}                         -1
&emsp;&emsp;v = 3, a = {3,7,4}                          0
</pre>

**Test Cases:**
1. v = 3, a = {3,7,4}, expected = 0

![image](https://user-images.githubusercontent.com/104089036/231792068-667f68b5-c439-47c7-9ebc-4c0b400f4be1.png)

Test case passed.

2. v = 8, a = {3,7,4}, expected = 3

![image](https://user-images.githubusercontent.com/104089036/231793356-d6e4e3c6-7c47-434a-815c-1f9793233c42.png)

Test case failed.

3. v = 3, a[] = {}, expected = -1 

![image](https://user-images.githubusercontent.com/104089036/231794391-9de1a979-2372-442d-b651-51061579e8f5.png)

Test case passed.

4. v = 7, a = {3,7,4}, expected = 1

![image](https://user-images.githubusercontent.com/104089036/231794774-10b50ce3-30e2-48ae-8ff3-206de7009f92.png)

Test case passed.
</br></br>

**P2.** The function countItem returns the number of times a value v appears in an array of integers a.</br>

<pre>
Java code:
public class lab7_2_class {
		public static int countItem(int v, int a[])
		{
		int count = 0;
		for (int i = 0; i < a.length; i++)
		{
		if (a[i] == v)
		count++;
		}
		return (count);
		}
	}
</pre>

<pre>
Equivalence Partitioning 
Tester Action and Input Data          Expected Outcome
&emsp;&emsp;v = 3, a = {3,7,4,3}                        2
&emsp;&emsp;v = 8, a = {3,7,4}                          0
&emsp;&emsp;v = 7, a = {3,7,4}                          1
</pre>

<pre>
Boundary Value Analysis
Tester Action and Input Data          Expected Outcome
&emsp;&emsp;v = 3, a = {}                               0
</pre>

**Test Cases:**
1. v = 3, a = {3,7,4,3}, expected = 2

![image](https://user-images.githubusercontent.com/104089036/231805866-f16194ff-dc69-4987-ad95-8122ac1f372d.png)

Test case passed.

2. v = 8, a = {3,7,4}, expected = 0

![image](https://user-images.githubusercontent.com/104089036/231806418-45ac76ba-1609-4146-aafd-c577c99e1934.png)

Test case passed.

3. v = 3, a[] = {}, expected = 0

![image](https://user-images.githubusercontent.com/104089036/231806545-083c6007-3240-4ef2-83fc-315705c1a7bd.png)

Test case passed.

4. v = 7, a = {3,7,4}, expected = 1

![image](https://user-images.githubusercontent.com/104089036/231806625-69496048-ef7e-4ae9-9ad2-465a56fc4175.png)

Test case passed.
</br></br>
**P3.** The function binarySearch searches for a value v in an ordered array of integers a. If v appears in the array a, then the function returns an index i, such that a[i] == v; otherwise, -1 is returned. Assumption: the elements in the array a are sorted in non-decreasing order.

<pre>
package Lab7_3;

public class Lab7_3_class {
	int binarySearch(int v, int a[])
	{
		int lo,mid,hi;
		lo = 0;
		hi = a.length-1;
		while (lo <= hi)
		{
			mid = (lo+hi)/2;
			if (v == a[mid])
				return (mid);
			else if (v < a[mid])
				hi = mid-1;
			else
				lo = mid+1;
		}
		return(-1);
	}
}
</pre>

<pre>
Equivalence Partitioning 
Tester Action and Input Data          Expected Outcome
&emsp;&emsp;v = 3, a = {3,7,4}                          0
&emsp;&emsp;v = 8, a = {3,7,4}                         -1
&emsp;&emsp;v = 4, a = {3,7,4,4}                      2 or 3
</pre>

<pre>
Boundary Value Analysis
Tester Action and Input Data          Expected Outcome
&emsp;&emsp;v = 3, a = {}                               -1
</pre>

**Test Cases:**
1. v = 3, a = {3,7,4}, expected = 0

![image](https://user-images.githubusercontent.com/104089036/231810347-0420eef1-6f2a-4b6b-a834-dcb678d222ca.png)

Test case passed.

2. v = 8, a = {3,7,4}, expected = -1

![image](https://user-images.githubusercontent.com/104089036/231810410-b5adafcd-620b-4e7c-8040-fada6bdc7d04.png)

Test case passed.

3. v = 3, a[] = {}, expected = -1

![image](https://user-images.githubusercontent.com/104089036/231810496-9da691ef-0107-4d0a-887d-1d9bb70f6727.png)

Test case passed.

4. v = 4, a[] = {3,7,4,4}, expected = 2

![image](https://user-images.githubusercontent.com/104089036/231810695-ce749220-efbc-4624-a5df-b606907dec08.png)

Test case failed.

</br></br>
**P4.** The following problem has been adapted from The Art of Software Testing, by G. Myers (1979). The function triangle takes three integer parameters that are interpreted as the lengths of the sides of a triangle. It returns whether the triangle is equilateral (three lengths equal), isosceles (two lengths equal),
scalene (no lengths equal), or invalid (impossible lengths).
<pre>
Java code:
package Lab7_4;

public class Lab7_4_class{
	final int EQUILATERAL = 0;
	final int ISOSCELES = 1;
	final int SCALENE = 2;
	final int INVALID = 3;
	public  int triangle(int a, int b, int c)
	{
	if (a >= b+c || b >= a+c || c >= a+b)
		return(INVALID);
	if (a == b && b == c)
		return(EQUILATERAL);
	if (a == b || a == c || b == c)
		return(ISOSCELES);
		return(SCALENE);

	}
}
</pre>

<pre>
Equivalence Partitioning 
Tester Action and Input Data          Expected Outcome
&emsp;&emsp;a=3, b=3, c=3                               0
&emsp;&emsp;a=2, b=3, c=1                               3
&emsp;&emsp;a=3, b=3, c=4                               1
&emsp;&emsp;a=5, b=3, c=4                               2
</pre>

<pre>
Boundary Value Analysis
Tester Action and Input Data          Expected Outcome
&emsp;&emsp;a=5, b=5, c=10                              3
&emsp;&emsp;a=2, b=3, c=1                               3
</pre>

**Test Cases:**
1. a=2, b=3, c=1, expected = 3

![image](https://user-images.githubusercontent.com/104089036/231816391-5f880cd8-1330-4daa-9cb0-62f229efbcbf.png)

Test case passed.

2. a=5, b=3, c=4, expected = 2

![image](https://user-images.githubusercontent.com/104089036/231816447-49125089-63f0-4fde-98ab-6d734039b49f.png)

Test case passed.

3. a=3, b=3, c=3, expected = 0

![image](https://user-images.githubusercontent.com/104089036/231816581-845a098b-a0a9-49c8-a72d-1db5dfbfb972.png)

Test case passed.

4. a=3, b=3, c=4, expected = 1

![image](https://user-images.githubusercontent.com/104089036/231816655-a8048cd0-14fa-47db-9dc4-67a8d1418fda.png)

Test case passed.
</br></br>

</br></br>
**P5.** The function prefix (String s1, String s2) returns whether or not the string s1 is a prefix of string s2 (you may assume that neither s1 nor s2 is null).</br>
<pre>
Java code:
package Lab7_5;

public class Lab7_5_class {
	public static boolean prefix(String s1, String s2)
	{
		if (s1.length() > s2.length())
		{
			return false;
		}
		for (int i = 0; i < s1.length(); i++)
		{
			if (s1.charAt(i) != s2.charAt(i))
			{
				return false;
			}
		}
		return true;
	}
}
</pre>

<pre>
Equivalence Partitioning 
Tester Action and Input Data          Expected Outcome
&emsp;&emsp;s1="pre", s2="prepare"                     true
&emsp;&emsp;s1="iso", s2="iso'                         true
&emsp;&emsp;s1="abd", s2="def"                         false
&emsp;&emsp;s1="x",s2=""                               false
</pre>

<pre>
Boundary Value Analysis
Tester Action and Input Data          Expected Outcome
&emsp;&emsp;s1="",s2="sample"                          true
&emsp;&emsp;s1="",s2=""                                true
</pre>

**Test cases**
1. s1="an", s2="analysis", expected=true

![image](https://user-images.githubusercontent.com/104089036/231820943-ba747492-d049-4da2-b7f0-79cf660e2588.png)

Test case passed.

2. s1="", s2="answer", expected=true

![image](https://user-images.githubusercontent.com/104089036/231820991-f7c4edf2-9cfa-4a08-a073-fcdecb85ae3c.png)

Test case passed.

3. s1="abd", s2="def", expected=false

![image](https://user-images.githubusercontent.com/104089036/231821046-16a526d3-8965-4858-9d51-ed2da9ae8ad2.png)

Test case passed.

4. s1="uwb", s2="", expected=false

![image](https://user-images.githubusercontent.com/104089036/231821109-7db0fb96-4c26-459b-ad3d-1dd9ffe9d13b.png)

Test case passed.
</br></br>
**P6.** Consider again the triangle classification program (P4) with a slightly different specification: The program reads floating values from the standard input. The three values A, B, and C are interpreted as representing the lengths of the sides of a triangle. The program then prints a message to the standard output that states whether the triangle, if it can be formed, is scalene, isosceles, equilateral, or right angled. Determine the following for the above program:</br>
a) Identify the equivalence classes for the system.</br>

<pre>
The following cases are covered in the equivalence classes:
For Equilateral triangles:
EC1 -> a=b, b=c

For Isosceles triangles: 
EC2 -> a!=b, a=c
EC3 -> a!=c, a=b
EC4 -> b!=a, b=c

For Scalene triangles: 
EC5 -> a!=b, b!=c, b!=c

For Right Angled triangles:
EC6 -> a^2 + b^2 = c^2
EC7 -> b^2 + c^2 = a^2
EC8 -> a^2 + c^2 = b^2

For invalid triangles:
EC9 -> a+b<=c
EC10 -> a+c<=b
EC11 -> b+c<=a

For all valid triangles:
EC12 -> a+b>=c
EC13 -> a+c>=b
EC14 -> b+c>=a
</pre>

b) Identify test cases to cover the identified equivalence classes. Also, explicitly mention which test case would cover which equivalence class.</br>
(Hint: you must need to be ensure that the identified set of test cases cover all identified equivalence classes)

<pre>
Test cases:
TC1 -> a=3.5, b=3.5, c=3.5
TC2 -> a=4.1, b=5, c=4.1
TC3 -> a=4.1, b=4.1, c=5
TC4 -> a=5, b=4.1, c=4.1
TC5 -> a=2, b=3, c=4
TC6 -> a=3.4, b=4.4, c=5.4
TC7 -> a=5.4, b=3.4, c=4.4
TC8 -> a=3.4, b=5.4, c=4.4
TC9 -> a=-1.4, b=2, c=3
TC10 -> a=2, b=3, c=0
TC11 -> a=3, b=1, c=2
TC12 -> a=3, b=4, c=3
TC13 -> a=3, b=5, a=4
TC14 -> a=2, b=3, c=4
</pre>
</br>
c) For the boundary condition A + B > C case (scalene triangle), identify test cases to verify the boundary.

<pre>
a=5, b=3, c=4
a=5, b=5, c=9.9
a=5, b=5, c=10.1
</pre>
</br>
d) For the boundary condition A = C case (isosceles triangle), identify test cases to verify the boundary.

<pre>
a=4, b=3, c=4
a=4, b=3, c=3.99
a=4, b=3, c=4.01
</pre>
</br>
e) For the boundary condition A = B = C case (equilateral triangle), identify test cases to verify the boundary.

<pre>
a=4, b=4, c=4
a=3.99, b=4, c=4
a=4, b=4, c=3.99
</pre>
</br>
f) For the boundary condition A<sup>2</sup> + B<sup>2</sup> = C<sup>2</sup> case (right-angle triangle), identify test cases to verify the boundary.

<pre>
a=3, b=4, c=5
a=3, b=4, c=5.1
a=3.1, b=4, c=5
</pre>
</br>
g) For the non-triangle case, identify test cases to explore the boundary.

<pre>
a=1, b=3, c=2
a=0, b=0, c=0
a=3, b=3, c=6
</pre>
</br>
h) For non-positive input, identify test points.

<pre>
a=0.7, b=3.7, c=-1.7
a=3, b=4, c=-8
a=0, b=4, c=5
</pre>
</br>
</br>

#### Section B:</br>
The code below is part of a method in the ConvexHull class in the VMAP system. The following is a small fragment of a method in the ConvexHull class. For the purposes of this exercise you do not need to know the intended function of the method. The parameter p is a Vector of Point objects, p.size() is the size of the vector p, (p.get(i)).x is the x component of the i<sup>th</sup> point appearing in p, similarly for (p.get(i)).y. This exercise is concerned with structural testing of code and so the focus is on creating test sets that satisfy some particular coverage criterion.</br>

<pre>
Vector doGraham (Vector p) {
  int i,j,min, M;
  
  Point t;
  min = 0;
  
  // search for minimum: 
  for(i=1; i < p.size(); ++i) {
    if(((Point) p.get(i)).y < ((Point) p.get(min)).y)
    {
      min= i;
    }
  }

  // continue along the values with same y component 
  for(i=0; i<p.size(); ++i) {
    if((((Point) p.get(i)).y == ((Point) p.get (min)).y) && (((Point) p.get(i)).x > ((Point) p.get(min)).x ))
    {
      min=i; 
    }
  }
</pre>

For the given code fragment you should carry out the following activities.
1. Convert the Java code comprising the beginning of the doGraham method into a control flow graph (CFG).

![Untitled Diagram (1)](https://user-images.githubusercontent.com/104089036/231838297-417532f7-2911-4501-b586-6f2eec618406.jpg)

<p align="center">Control Flow Graph of doGraham method</p>
For decision nodes, the left branch is when the node evaluates to True and the right part is when the node evaluates to False.</br>

2. Construct test sets for your flow graph that are adequate for the following criteria:</br>
  a. Statement Coverage.</br>
  b. Branch Coverage.</br>
  c. Basic Condition Coverage.</br>
   Let the re-written code with line numbers for statements be as follows:
   ![image](https://user-images.githubusercontent.com/104089036/231846384-ae51b9a6-e9a5-40bc-b43c-3c8c3d37d484.png)
   
   <pre>
   The test cases and their corresponding coverages of statements is shown as follows:
   1. p=[(x=2,y=4),(x=2,y=3),(x=3,y=1),(x=1,y=4)]
      Statements covered = {1,2,3,4,5,7,8}
      Branches covered = {5,8}
      Basic conditions covered = {5-false, 8-false}
   2. p=[(x=2,y=2),(x=2,y=3),(x=1,y=3),(x=1,y=4)]
      Statements covered = {1,2,3,4,5,7,8}
      Branches covered = {5,8}
      Basic conditions covered = {5-false, 8-false}
   3. p=[(x=1,y=5),(x=2,y=7),(x=3,y=5),(x=4,y=5),(x=5,y=6)]
      Statements covered = { 1,2,3,4,5,6,7,8,9}
      Branches covered = {5,8}
      Basic conditions covered = {5-false,true, 8-false,true}
   4. p=[(x=1,y=2)]
      Statements covered = {1,2,3,7,8}
      Branches covered = {8}
      Basic conditions covered = {}
   5. p=[]
      Statements covered = { 1,2,3}
      Branches covered = {}
      Basic conditions covered = {}
      
      Thus, the above 5 test cases are covering all statements, branches and conditions.
      These 5 test cases are adequate for statement coverage,branch coverage and basic condition coverage.
      </pre>
