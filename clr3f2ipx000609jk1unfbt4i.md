---
title: "MiQ Digital Intern Software Engineer 2023 OA"
seoTitle: "MiQ Digital Intern Software Engineer 2023 OA"
seoDescription: "MiQ Digital Intern Software Engineer 2023 OA, MIQ online test, MIQ OA"
datePublished: Sun Jan 07 2024 11:34:39 GMT+0000 (Coordinated Universal Time)
cuid: clr3f2ipx000609jk1unfbt4i
slug: miq-digital-intern-software-engineer-2023-oa
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1704626969329/fabc6ddc-01d0-4545-b1b3-ba0a1a02ceff.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1704627013561/d2c32aac-0790-4e5a-ad7f-7c9008283ec2.jpeg
tags: interview, javascript, web-development, webdev, sql, reactjs

---

MIQ Online test was conducted on Hackerrank. There was 1 DSA question and 2 SQL question and time limit is 1 hour only.

**Q1. DSA Question of array**

```cpp
Function Description

Complete the function countAnalogousArrays in the editor below.

 

countAnalogousArrays has the following parameter(s):

    int consecutiveDifference[n]:  the differences between each pair of consecutive integers in the secret array

    int lowerBound: an integer

    int upperBound: an integer

Returns:

    int: the number of arrays that are analogous to the secret array

 

Constraints

-109 ≤ lowerBound ≤ upperBound ≤ 109
1 ≤ n ≤ 105
-2*109 ≤ consecutiveDifference[i] ≤ 2*109
 

Input Format For Custom Testing
The first line contains an integer, n, that denotes the number of elements in consecutiveDifference.

Each line i of the n subsequent lines contains an integer, consecutiveDifference[i], where 0 ≤ i < n.

The next line contains an integer, lowerBound.

The last line contains an integer, upperBound.

Sample Case 0
Sample Input For Custom Testing

STDIN      Function
-----      --------
3     →    consecutiveDifferences[] size n = 3
-1    →    consecutiveDifferences = [-1, -3, 2]
-3
2
2     →    lowerBound = 2
8     →    upperBound = 8
Sample Output

3
Explanation

 

All possible analogous arrays are:

[3, 4, 7, 5]

[2, 3, 6, 4]

[4, 5, 8, 6]

 

Thus, the answer is 3.

Sample Case 1
Sample Input For Custom Testing

STDIN     Function
-----     --------
2    →    consecutiveDifferences[] size n = 2
1    →    consecutiveDifferences = [1, 2]
2
3    →    lowerBound = 3
4    →    upperBound = 4
Sample Output

0
Explanation

There is no array which is analogous to the secret array.
```

Ans.

```cpp
#include <iostream>
#include <vector>
using namespace std;

long long countAnalogousArrays(vector<int> consecutiveDifference, int lowerBound, int upperBound) {
    int n = consecutiveDifference.size();
    long long ans = 1; // Initialize with 1 since there's always one valid array (secret array).

    for (int i = 0; i < n; i++) {
        int diff = consecutiveDifference[i];

        // Calculate the possible range of values for the current element.
        int minValue = lowerBound - diff;
        int maxValue = upperBound - diff;

        // Update the lowerBound and upperBound for the next element.
        lowerBound = max(minValue, lowerBound);
        upperBound = min(maxValue, upperBound);

        // If lowerBound is greater than upperBound, there are no valid arrays.
        if (lowerBound > upperBound) {
            return 0;
        }

        // Add the number of valid values for the current element to the answer.
        ans *= (upperBound - lowerBound + 1);
    }

    return ans;
}

int main() {
    int n;
    cin >> n;
    vector<int> consecutiveDifference(n);
    for (int i = 0; i < n; i++) {
        cin >> consecutiveDifference[i];
    }
    int lowerBound, upperBound;
    cin >> lowerBound >> upperBound;

    long long result = countAnalogousArrays(consecutiveDifference, lowerBound, upperBound);
    cout << result << endl;

    return 0;
}
```

Q2.

```sql
Given two tables, Employee and Department, generate a summary of how many employees are in each department. Each department should be listed, whether they currently have any employees or not. The results should be sorted from high to low by number of employees, and then alphabetically by department when departments have the same number of employees. The results should list the department name followed by the employee count. The column names are not tested, so use whatever is appropriate.

 

Schema
EMPLOYEE
Name	Type	Description
ID	Integer	Employee ID number. This is a primary key.
NAME	String	Employee name
SALARY	Integer	Employee salary
DEPT_ID	Integer	ID of the employee's department, a foreign key to DEPARTMENT.ID.
DEPARTMENT
Name	Type	Description
ID	Integer	Department ID. This is a primary key.
NAME	String	Department name.
LOCATION	String	Department location.
Sample Data Tables
EMPLOYEE
ID	NAME	SALARY	DEPT_ID
1	Candice	4685	1
2	Julia	2559	2
3	Bob	4405	4
4	Scarlet	2350	1
5	Ileana	1151	4
DEPARTMENT
ID	NAME	LOCATION
1	Executive	Sydney
2	Production	Sydney
3	Resources	Cape Town
4	Technical	Texas
5	Management	Paris
 

Sample Output

 

Executive 2

Technical 2

Production 1

Management 0

Resources 0
```

Ans.

```sql
SELECT D.NAME AS Department, COUNT(E.ID) AS EmployeeCount
FROM DEPARTMENT D
LEFT JOIN EMPLOYEE E ON D.ID = E.DEPT_ID
GROUP BY D.NAME
ORDER BY EmployeeCount DESC, Department;
```

Q3

```sql
A university maintains data on professors and departments in two tables: PROFESSOR and DEPARTMENT. Write a query to print the NAME and SALARY for each professor who satisfies the following two requirements:

The professor does not work in the Arts and Humanities department.
The professor's salary is greater than the smallest salary of any professor in the Arts and Humanities department.
The name must be printed before the salary, but row order does not matter.

 
Schema
DEPARTMENT
Name	Type	Description
ID	Integer	A department ID in the inclusive range [1, 1000]. This is a primary key.
NAME	String	A department name. This field contains between 1 and 100 characters.
PROFESSOR
Name	Type	Description
ID	Integer	A professor's ID in the inclusive range [1, 1000]. This is a primary key.
NAME	String	A professor's name. This field contains between 1 and 100 characters.
DEPARTMENT_ID	Integer	A professor's department ID. This is a foreign key to DEPARTMENT.ID.
SALARY	Integer	A professor's salary in the inclusive range [5000, 40000].
Sample Data Tables
DEPARTMENT
ID	NAME
3	Biological Sciences
5	Technology
6	Humanities & Social Sciences
2	Clinical Medicine
4	Arts and Humanities
1	Physical Sciences
PROFESSOR
ID	NAME	DEPARTMENT_ID	SALARY
1	Shauna Rivera	1	22606
8	Ruth Price	3	9287
9	Julie Gonzalez	4	18870
2	Craig Elliott	5	27524
10	Scott Butler	1	26200
3	Nancy Russell	2	7076
4	Clarence Johnson	1	7249
7	Louis Schmidt	1	13437
5	Terri Thompson	3	28432
6	Keith Gilbert	5	12610
 

Sample Output

Shauna Rivera 22606
Craig Elliott 27524
Terri Thompson 28432
Scott Butler 26200
 

Explanation

Julie Gonzalez has a salary of 18870, which is smaller than the salary of any other professor in the Arts and Humanities department. The following employees of other departments have salaries higher than Julie's:

Shauna Rivera's salary of 22606 is higher than Julie Gonzalez's.
Craig Elliott's salary of 27524 is higher than Julie Gonzalez's.
Terri Thompson's salary of 28432 is higher than Julie Gonzalez's.
Scott Butler's salary of 26200 is higher than Julie Gonzalez's.
```

Ans.

```sql
SELECT P.NAME, P.SALARY
FROM PROFESSOR P
WHERE P.DEPARTMENT_ID NOT IN (
    SELECT D.ID
    FROM DEPARTMENT D
    WHERE D.NAME = 'Arts and Humanities'
)
AND P.SALARY > (
    SELECT MIN(PH.SALARY)
    FROM PROFESSOR PH
    WHERE PH.DEPARTMENT_ID IN (
        SELECT D.ID
        FROM DEPARTMENT D
        WHERE D.NAME = 'Arts and Humanities'
    )
);
```