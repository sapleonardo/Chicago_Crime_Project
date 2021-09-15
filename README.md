
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

