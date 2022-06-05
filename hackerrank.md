# Exercise from [Solve SQL | HackerRank](https://www.hackerrank.com/domains/sql)
**Solve problems using MySQL**

---
### →[Revising the Select Query I](https://www.hackerrank.com/challenges/revising-the-select-query/problem?isFullScreen=true)

Query all columns for all American cities in the CITY table with populations larger than 100000. The CountryCode for America is USA.

The CITY table is described as follows:

|  Field        | Type          |
|-------        |------         |
| ID            | NUMBER        |
| NAME          | VARCHAR2(17)  |
| COUNTRY CODE  | VARCHAR2(3)   |
| DISTRICT      | VARCHAR2(20) |
| POPULATION    | NUMBER        |

```sql
SELECT * FROM CITY WHERE POPULATION > 100000 AND COUNTRYCODE = "USA";
```

---

### →[Revising the Select Query II](https://www.hackerrank.com/challenges/revising-the-select-query-2/problem?isFullScreen=true)
Query the NAME field for all American cities in the CITY table with populations larger than 120000. The CountryCode for America is USA.

The CITY table is described as follows:

|  Field        | Type          |
|-------        |------         |
| ID            | NUMBER        |
| NAME          | VARCHAR2(17)  |
| COUNTRY CODE  | VARCHAR2(3)   |
| DISTRICT      | VARCHAR2(20)  |
| POPULATION    | NUMBER        |


```sql
SELECT NAME FROM CITY WHERE POPULATION > 120000 AND COUNTRYCODE = "USA";
```

---

### →[Select All](https://www.hackerrank.com/challenges/select-all-sql/problem?isFullScreen=true)
Query all columns (attributes) for every row in the CITY table.

The CITY table is described as follows:

|  Field        | Type          |
|-------        |------         |
| ID            | NUMBER        |
| NAME          | VARCHAR2(17)  |
| COUNTRY CODE  | VARCHAR2(3)   |
| DISTRICT      | VARCHAR2(20)  |
| POPULATION    | NUMBER        |


```sql
SELECT * FROM CITY;
```

---

### →[Select By ID](https://www.hackerrank.com/challenges/select-by-id/problem?isFullScreen=true)
Query all columns for a city in CITY with the ID 1661.

The CITY table is described as follows:

|  Field        | Type          |
|-------        |------         |
| ID            | NUMBER        |
| NAME          | VARCHAR2(17)  |
| COUNTRY CODE  | VARCHAR2(3)   |
| DISTRICT      | VARCHAR2(20)  |
| POPULATION    | NUMBER        |


```sql
SELECT * FROM CITY WHERE ID = 1661;
```

---

### →[Japanese Cities' Attributes](https://www.hackerrank.com/challenges/japanese-cities-attributes/problem?isFullScreen=true)
Query all attributes of every Japanese city in the CITY table. The COUNTRYCODE for Japan is JPN.

The CITY table is described as follows:

|  Field        | Type          |
|-------        |------         |
| ID            | NUMBER        |
| NAME          | VARCHAR2(17)  |
| COUNTRY CODE  | VARCHAR2(3)   |
| DISTRICT      | VARCHAR2(20)  |
| POPULATION    | NUMBER        |


```sql
SELECT * FROM CITY WHERE COUNTRYCODE = "JPN";
```

---

### →[Japanese Cities' Names](https://www.hackerrank.com/challenges/japanese-cities-name?isFullScreen=true)
Query the names of all the Japanese cities in the CITY table. The COUNTRYCODE for Japan is JPN.

The CITY table is described as follows:

|  Field        | Type          |
|-------        |------         |
| ID            | NUMBER        |
| NAME          | VARCHAR2(17)  |
| COUNTRY CODE  | VARCHAR2(3)   |
| DISTRICT      | VARCHAR2(20)  |
| POPULATION    | NUMBER        |


```sql
SELECT NAME FROM CITY WHERE COUNTRYCODE = "JPN";
```

---

### →[Weather Observation Station 1](https://www.hackerrank.com/challenges/weather-observation-station-1/problem?isFullScreen=true)
Query a list of CITY and STATE from the STATION table.

The STATION table is described as follows:


|  Field | Type         |
|------- |------        |
| ID     | NUMBER       |
| CITY   | VARCHAR2(21) |
| STATE  | VARCHAR2(2)  |
| LAT_N  | NUMBER       |
| LONG_W | NUMBER       |

where LAT_N is the northern latitude and LONG_W is the western longitude.


```sql
SELECT CITY, STATE FROM STATION;
```

---

### →[Weather Observation Station 2](https://www.hackerrank.com/challenges/weather-observation-station-2/problem?isFullScreen=true)
Query the following two values from the STATION table:

1. The sum of all values in LAT_N rounded to a scale of  decimal places.
2. The sum of all values in LONG_W rounded to a scale of  decimal places.

Input Format

The STATION table is described as follows:


|  Field | Type         |
|------- |------        |
| ID     | NUMBER       |
| CITY   | VARCHAR2(21) |
| STATE  | VARCHAR2(2)  |
| LAT_N  | NUMBER       |
| LONG_W | NUMBER       |

where LAT_N is the northern latitude and LONG_W is the western longitude.


```sql
SELECT ROUND(SUM(LAT_N), 2) AS LAT, ROUND(SUM(LONG_W),2) AS LON FROM STATION;
```

---

### →[Weather Observation Station 3](https://www.hackerrank.com/challenges/weather-observation-station-3/problem?isFullScreen=true)
Query a list of CITY names from STATION for cities that have an even ID number. Print the results in any order, but exclude duplicates from the answer.

Input Format

The STATION table is described as follows:


|  Field | Type         |
|------- |------        |
| ID     | NUMBER       |
| CITY   | VARCHAR2(21) |
| STATE  | VARCHAR2(2)  |
| LAT_N  | NUMBER       |
| LONG_W | NUMBER       |

where LAT_N is the northern latitude and LONG_W is the western longitude.


```sql
SELECT DISTINCT CITY FROM STATION WHERE MOD(ID, 2) = 0 ORDER BY CITY ASC;
```

---

### →[Weather Observation Station 4](https://www.hackerrank.com/challenges/weather-observation-station-4/problem?isFullScreen=true)
Find the difference between the total number of CITY entries in the table and the number of distinct CITY entries in the table.

Input Format

The STATION table is described as follows:


|  Field | Type         |
|------- |------        |
| ID     | NUMBER       |
| CITY   | VARCHAR2(21) |
| STATE  | VARCHAR2(2)  |
| LAT_N  | NUMBER       |
| LONG_W | NUMBER       |

where LAT_N is the northern latitude and LONG_W is the western longitude.


```sql
SELECT COUNT(CITY) - COUNT(DISTINCT CITY) FROM STATION;
```

---

### →[Weather Observation Station 5](https://www.hackerrank.com/challenges/weather-observation-station-5/problem?isFullScreen=true)
Query the two cities in STATION with the shortest and longest CITY names, as well as their respective lengths (i.e.: number of characters in the name). If there is more than one smallest or largest city, choose the one that comes first when ordered alphabetically.
Input Format

The STATION table is described as follows:


|  Field | Type         |
|------- |------        |
| ID     | NUMBER       |
| CITY   | VARCHAR2(21) |
| STATE  | VARCHAR2(2)  |
| LAT_N  | NUMBER       |
| LONG_W | NUMBER       |

where LAT_N is the northern latitude and LONG_W is the western longitude.


```sql
SELECT CITY, LENGTH(CITY) AS lengthOfCity FROM STATION ORDER BY lengthOfCity DESC, CITY ASC LIMIT 1;
SELECT CITY, LENGTH(CITY) AS lengthOfCity FROM STATION ORDER BY lengthOfCity ASC, CITY ASC LIMIT 1;
```

---

### →[Weather Observation Station 6](https://www.hackerrank.com/challenges/weather-observation-station-6/problem?isFullScreen=true)
Query the list of CITY names starting with vowels (i.e., a, e, i, o, or u) from STATION. Your result cannot contain duplicates.
Input Format

The STATION table is described as follows:


|  Field | Type         |
|------- |------        |
| ID     | NUMBER       |
| CITY   | VARCHAR2(21) |
| STATE  | VARCHAR2(2)  |
| LAT_N  | NUMBER       |
| LONG_W | NUMBER       |

where LAT_N is the northern latitude and LONG_W is the western longitude.


```sql
SELECT CITY FROM STATION WHERE CITY REGEXP '^[AEIOU]\w*';
```

---

### →[Weather Observation Station 7](https://www.hackerrank.com/challenges/weather-observation-station-7/problem?isFullScreen=true)
Query the list of CITY names ending with vowels (a, e, i, o, u) from STATION. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:


|  Field | Type         |
|------- |------        |
| ID     | NUMBER       |
| CITY   | VARCHAR2(21) |
| STATE  | VARCHAR2(2)  |
| LAT_N  | NUMBER       |
| LONG_W | NUMBER       |

where LAT_N is the northern latitude and LONG_W is the western longitude.


```sql
SELECT DISTINCT CITY FROM STATION WHERE CITY REGEXP '\w*[aeiou]$';
```


---

### →[Weather Observation Station 8](https://www.hackerrank.com/challenges/weather-observation-station-8/problem?isFullScreen=true)
Query the list of CITY names from STATION which have vowels (i.e., a, e, i, o, and u) as both their first and last characters. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:


|  Field | Type         |
|------- |------        |
| ID     | NUMBER       |
| CITY   | VARCHAR2(21) |
| STATE  | VARCHAR2(2)  |
| LAT_N  | NUMBER       |
| LONG_W | NUMBER       |

where LAT_N is the northern latitude and LONG_W is the western longitude.


```sql
SELECT DISTINCT CITY FROM STATION WHERE CITY REGEXP '^[aeiou].*[aeiou]$';
```

---

### →[Weather Observation Station 9](https://www.hackerrank.com/challenges/weather-observation-station-9/problem?isFullScreen=true)
Query the list of CITY names from STATION that do not start with vowels. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:


|  Field | Type         |
|------- |------        |
| ID     | NUMBER       |
| CITY   | VARCHAR2(21) |
| STATE  | VARCHAR2(2)  |
| LAT_N  | NUMBER       |
| LONG_W | NUMBER       |

where LAT_N is the northern latitude and LONG_W is the western longitude.


```sql
SELECT DISTINCT CITY FROM STATION WHERE CITY REGEXP '^[^AEIOU]\w*';
```


---

### →[Weather Observation Station 10](https://www.hackerrank.com/challenges/weather-observation-station-10/problem?isFullScreen=true)
Query the list of CITY names from STATION that do not end with vowels. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:


|  Field | Type         |
|------- |------        |
| ID     | NUMBER       |
| CITY   | VARCHAR2(21) |
| STATE  | VARCHAR2(2)  |
| LAT_N  | NUMBER       |
| LONG_W | NUMBER       |

where LAT_N is the northern latitude and LONG_W is the western longitude.


```sql
SELECT DISTINCT CITY FROM STATION WHERE CITY REGEXP '\w*[^aeiou]$';
```

---

### →[Weather Observation Station 11](https://www.hackerrank.com/challenges/weather-observation-station-11/problem?isFullScreen=true)
Query the list of CITY names from STATION that either do not start with vowels or do not end with vowels. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:


|  Field | Type         |
|------- |------        |
| ID     | NUMBER       |
| CITY   | VARCHAR2(21) |
| STATE  | VARCHAR2(2)  |
| LAT_N  | NUMBER       |
| LONG_W | NUMBER       |

where LAT_N is the northern latitude and LONG_W is the western longitude.


```sql
SELECT DISTINCT CITY FROM STATION WHERE CITY REGEXP '^[^aeiou].*[^aeiou]$';
```

---

### →[Weather Observation Station 12](https://www.hackerrank.com/challenges/weather-observation-station-12/problem?isFullScreen=true)
Query the list of CITY names from STATION that do not start with vowels and do not end with vowels. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:


|  Field | Type         |
|------- |------        |
| ID     | NUMBER       |
| CITY   | VARCHAR2(21) |
| STATE  | VARCHAR2(2)  |
| LAT_N  | NUMBER       |
| LONG_W | NUMBER       |


```sql
SELECT DISTINCT CITY FROM STATION WHERE CITY REGEXP '^[^AEIOU].*[^aeiou]$';
```

---

### →[Higher Than 75 Marks](https://www.hackerrank.com/challenges/more-than-75-marks/problem?isFullScreen=true)
Query the Name of any student in STUDENTS who scored higher than  Marks. Order your output by the last three characters of each name. If two or more students both have names ending in the same last three characters (i.e.: Bobby, Robby, etc.), secondary sort them by ascending ID.

Input Format

The STATION table is described as follows:


|  Field | Type     |
|------- |------    |
| ID     | Integer  |
| Name   | String   |
| Marks  | Integer  |



```sql
SELECT NAME FROM STUDENTS WHERE Marks > 75 ORDER BY SUBSTRING(NAME, LENGTH(NAME)-2, 3) ASC, ID ASC;
```


---

### →[Employee Names](https://www.hackerrank.com/challenges/name-of-employees/problem?isFullScreen=true&h_r=next-challenge&h_v=zen&h_r=next-challenge&h_v=zen)
Write a query that prints a list of employee names (i.e.: the name attribute) from the Employee table in alphabetical order.

Input Format

The Employee table containing employee data for a company is described as follows:


|  Field      | Type     |
|-------      |------    |
| employee_id | INTEGER  |
| name        | STRING   |
| months      | INTEGER  |
| salary      | INTEGER  |


```sql
SELECT NAME FROM Employee ORDER BY NAME;
```

---

### →[Employee Salaries](https://www.hackerrank.com/challenges/salary-of-employees/problem?isFullScreen=true&h_r=next-challenge&h_v=zen&h_r=next-challenge&h_v=zen&h_r=next-challenge&h_v=zen)
Write a query that prints a list of employee names (i.e.: the name attribute) for employees in Employee having a salary greater than $2000 per month who have been employees for less than 10 months. Sort your result by ascending employee_id.

Input Format

The Employee table containing employee data for a company is described as follows:


|  Field      | Type     |
|-------      |------    |
| employee_id | INTEGER  |
| name        | STRING   |
| months      | INTEGER  |
| salary      | INTEGER  |


```sql
SELECT name FROM Employee WHERE salary > 2000 and months < 10 ORDER BY employee_id ASC;
```

---

### →[Revising Aggregations - Averages](https://www.hackerrank.com/challenges/revising-aggregations-the-average-function/problem?isFullScreen=true&h_r=next-challenge&h_v=zen&h_r=next-challenge&h_v=zen&h_r=next-challenge&h_v=zen&h_r=next-challenge&h_v=zen)
Query the average population of all cities in CITY where District is California.

Input Format


|  Field        | Type          |
|-------        |------         |
| ID            | NUMBER        |
| NAME          | VARCHAR2(17)  |
| COUNTRY CODE  | VARCHAR2(3)   |
| DISTRICT      | VARCHAR2(20) |
| POPULATION    | NUMBER        |

```sql
SELECT AVG(POPULATION) FROM CITY WHERE DISTRICT = "California";
```

---

### →[Type of Triangle](https://www.hackerrank.com/challenges/what-type-of-triangle/problem?isFullScreen=true)
Write a query identifying the type of each record in the TRIANGLES table using its three side lengths. Output one of the following statements for each record in the table:

  - Equilateral: It's a triangle with 3 sides of equal length.
  - Isosceles: It's a triangle with 2 sides of equal length.
  - Scalene: It's a triangle with 3 sides of differing lengths.
  - Not A Triangle: The given values of A, B, and C don't form a triangle.

The TRIANGLES table is described as follows:


|  Column | Type    |
|-------  |------   |
| A       | INTEGER |
| B       | INTEGER |
| C       | INTEGER |


```sql
SELECT
  CASE
    WHEN A + B <= C OR A + C <= B OR B + C <= A THEN 'Not A Triangle'
    WHEN A = B AND B = C THEN "Equilateral"
    WHEN A = B OR A = C OR B = C THEN "Isosceles"
    ELSE "Scalene"
  END
FROM TRIANGLES
```
