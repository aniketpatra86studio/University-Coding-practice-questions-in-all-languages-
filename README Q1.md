# Netflix Movie Recommendation System

## Problem Statement
You are developing a simple Netflix Movie Recommendation System. The system stores a list of movie names and their corresponding ratings in two arrays:
- A **String array** containing movie names.
- A **double array** containing the ratings of those movies.

The rating at each index corresponds to the movie at the same index.

The user enters a minimum rating. Your program must display all movies whose rating is **greater than or equal to** the minimum rating, along with the movie name and rating.

## Input Format
```
Line 1:         N              (integer — number of movies)
Line 2 to N+1:  <MovieName> <Rating>   (one movie per line, space-separated)
Line N+2:       R              (double — minimum rating required)
```

## Constraints
- 1 ≤ N ≤ 100
- 0.0 ≤ Rating ≤ 10.0
- 0.0 ≤ R ≤ 10.0
- Movie names contain no spaces.

## Output Format
- Display all movies whose rating is >= R, one per line, in the format:
```
MovieName - Rating
```
- If no movie satisfies the minimum rating, display:
```
No movies found
```

## Sample Input
```
5
Inception 8.8
Titanic 7.8
Avatar 7.9
Joker 8.5
Tenet 7.3
8.0
```

## Sample Output
```
Inception - 8.8
Joker - 8.5
```

## Solution (Java)

```java
import java.io.*;
import java.util.*;
import java.text.*;
import java.math.*;
import java.util.regex.*;

public class Solution {

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = Integer.parseInt(sc.nextLine().trim());

        String[] names = new String[n];
        double[] ratings = new double[n];

        for (int i = 0; i < n; i++) {
            String[] parts = sc.nextLine().trim().split("\\s+");
            names[i] = parts[0];
            ratings[i] = Double.parseDouble(parts[1]);
        }

        double r = Double.parseDouble(sc.nextLine().trim());

        boolean found = false;
        for (int i = 0; i < n; i++) {
            if (ratings[i] >= r) {
                System.out.println(names[i] + " - " + ratings[i]);
                found = true;
            }
        }

        if (!found) {
            System.out.println("No movies found");
        }
    }
}
```
