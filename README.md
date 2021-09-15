
![Chicago_Pictures](https://user-images.githubusercontent.com/85455439/133498473-b822f98a-ecca-49bb-9f9b-f5cb7d12ef18.jpg)


# Chicago_Crime_Project # 

## The goal of this analysis was to analysis crime data gathered from Chicago and answer three essential questions ##

###### 1: What were the total number of cases and what was the percentage which ended up in convictions? ######

###### 2: Is there a correlation between domestic cases and a higher rate of conviction? ###### 

###### 3: Which of Chicagos wards is the most violent? ###### 


## The following is an introduction to the dataset along with the columns of importance ## 

```sql 
SELECT case_number AS cases 
FROM bigquery-public-data.chicago_crime.crime LIMIT 5;
```
| cases    |
| -------- |
| HY440240 |
| HY470758 |
| HY473735 |
| HY509904 |
| HY323457 |


###### The column "cases" shows the unique case_number pertaining to each incident documented by the chicago police department ######



```sql
SELECT arrest AS conviction_or_no 
FROM bigquery-public-data.chicago_crime.crime
LIMIT 5; 
```
| conviction\_or\_no |
| ------------------ |
| true               |
| false              |
| true               |
| true               |
| false              |

###### The column "conviction/_or/_no" returns a value of "true" if the case in question resulted in a conviction and "false" if there was no conviction #######


```sql 

SELECT domestic as domestic_cases 
FROM bigquery-public-data.chicago_crime.crime LIMIT 5; 
```
| domestic\_cases |
| --------------- |
| false           |
| true            |
| false           |
| false           |
| false           |
###### The column "domestic\_cases" returns a value of "true" if the case was domestic and a value of "fasle" if the case wasn't domestic ######


```sql
SELECT ward FROM bigquery-public-data.chicago_crime.crime LIMIT 10; 
```
| ward |
| ---- |
| 9    |
| 11   |
| 10   |
| 9    |
| 23   |
| 45   |
| 9    |
| 45   |
| 5    |
| 25   |
###### The column "ward" returns the ward where each case was reported ######


```sql 
SELECT COUNT(DISTINCT case_number) AS cases_recorded 
FROM bigquery-public-data.chicago_crime.crime; 
``` 
| cases\_recorded |
| --------------- |
| 7397149         |
###### The column "cases_recorded" returns the value of the total number of cases in this dataset which were catalogued by the chicago police department ######


## Chicago Crime Analysis Part One: What were the total number of cases? What percentage resulted in a conviction? ## 

```sql 
SELECT COUNT(arrest) AS convictions 
FROM bigquery-public-data.chicago_crime.crime
WHERE arrest = true
```
| convictions |
| ----------- |
| 1988502     |
###### Out of the total number of cases, almost two million out of over 7 million cases resulted in a conviction ######
