# Employee Bonus Eligibility

## Problem Statement
You are building an HR tool to identify employees eligible for a performance bonus. The system stores employee names and their performance scores in two arrays:

* A String array containing employee names.
* A double array containing performance scores (out of 10.0).

The score at each index corresponds to the employee at the same index.
The user enters a minimum eligibility score. Your program must display all employees whose score is strictly greater than the eligibility score, along with their name and score.

## Input Format
```
Line 1:         N              (integer — number of employees)
Line 2 to N+1:  <EmployeeName> <Score>   (one employee per line, space-separated)
Line N+2:       E              (double — eligibility score)
```

## Constraints
* 1 ≤ N ≤ 100
* 0.0 ≤ Score ≤ 10.0
* 0.0 ≤ E ≤ 10.0
* Employee names contain no spaces.

## Output Format
* Display all employees whose score is strictly > E, one per line, in the format:
```
EmployeeName - Score
```
* If no employee is eligible, display:
```
No employees eligible
```

## Sample Input
```
4
Sneha 8.5
Rahul 6.2
Priya 9.1
Aman 7.0
7.0
```

## Sample Output
```
Sneha - 8.5
Priya - 9.1
```

## Solution (Java)
```java
import java.util.*;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = Integer.parseInt(sc.nextLine().trim());

        String[] names = new String[n];
        double[] scores = new double[n];

        for (int i = 0; i < n; i++) {
            String[] parts = sc.nextLine().trim().split("\\s+");
            names[i] = parts[0];
            scores[i] = Double.parseDouble(parts[1]);
        }

        double e = Double.parseDouble(sc.nextLine().trim());

        boolean found = false;
        for (int i = 0; i < n; i++) {
            if (scores[i] > e) {
                System.out.println(names[i] + " - " + scores[i]);
                found = true;
            }
        }

        if (!found) {
            System.out.println("No employees eligible");
        }
    }
}
```
