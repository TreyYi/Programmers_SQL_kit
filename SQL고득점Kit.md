### 프로그래머스 SQL 고득점 Kit

1) 모든 레코드 조회하기 (https://programmers.co.kr/learn/courses/30/lessons/59034)

- ```sql
  SELECT * FROM ANIMAL_INS ORDER BY ANIMAL_ID;

2) 역순 정렬하기 (https://programmers.co.kr/learn/courses/30/lessons/59035)

- ```sql
  SELECT NAME, DATETIME FROM ANIMAL_INS ORDER BY ANIMAL_ID DESC;

3) 아픈 동물 찾기 (https://programmers.co.kr/learn/courses/30/lessons/59036)

- ```sql
  SELECT ANIMAL_ID, NAME FROM ANIMAL_INS WHERE INTAKE_CONDITION='Sick' ORDER BY ANIMAL_ID;

4) 어린 동물 찾기 (https://programmers.co.kr/learn/courses/30/lessons/59037)

- ```sql
  SELECT ANIMAL_ID, NAME FROM ANIMAL_INS WHERE NOT INTAKE_CONDITION = 'Aged' ORDER BY ANIMAL_ID;
  ```

5) 동물의 아이디와 이름 (https://programmers.co.kr/learn/courses/30/lessons/59403)

- ```sql
  SELECT ANIMAL_ID, NAME FROM ANIMAL_INS ORDER BY ANIMAL_ID;
  ```

6) 여러 기준으로 정렬하기 (https://programmers.co.kr/learn/courses/30/lessons/59404)

- ```sql
  SELECT ANIMAL_ID, NAME, DATETIME FROM ANIMAL_INS ORDER BY NAME, DATETIME DESC;
  ```

7) 상위 n개 레코드 (https://programmers.co.kr/learn/courses/30/lessons/59405)

- ```sql
  SELECT NAME FROM ANIMAL_INS ORDER BY DATETIME LIMIT 1;
  ```

8) 최댓값 구하기 (https://programmers.co.kr/learn/courses/30/lessons/59415)

- ```sql
  SELECT DATETIME AS "시간" FROM ANIMAL_INS ORDER BY DATETIME DESC LIMIT 1;
  ```

9) 최솟값 구하기 (https://programmers.co.kr/learn/courses/30/lessons/59038)

- ```sql
  SELECT DATETIME AS "시간" FROM ANIMAL_INS ORDER BY DATETIME LIMIT 1;
  ```

10) 동물 수 구하기 (https://programmers.co.kr/learn/courses/30/lessons/59406)

- ```sql
  SELECT COUNT(ANIMAL_ID) AS count FROM ANIMAL_INS;
  ```

11) 중복 제거하기 (https://programmers.co.kr/learn/courses/30/lessons/59408)

- ```sql
  SELECT COUNT(DISTINCT NAME) AS "count" FROM ANIMAL_INS 
  WHERE NAME IS NOT NULL;
  ```

12) 고양이와 개는 몇마리 있을까 (https://programmers.co.kr/learn/courses/30/lessons/59040)

- ```sql
  SELECT ANIMAL_TYPE, COUNT(ANIMAL_TYPE) AS "count" FROM ANIMAL_INS
  GROUP BY ANIMAL_TYPE ORDER BY ANIMAL_TYPE;
  ```

13) 동명 동물 수 찾기 (https://programmers.co.kr/learn/courses/30/lessons/59041)

- ```sql
  SELECT NAME, COUNT(NAME) FROM ANIMAL_INS
  WHERE NAME IS NOT NULL
  GROUP BY NAME
  HAVING COUNT(NAME) > 1
  ORDER BY NAME
  ```

14) 입양 시각 구하기(1) (https://programmers.co.kr/learn/courses/30/lessons/59412)

- ```sql
  SELECT HOUR(DATETIME) AS "HOUR", COUNT(ANIMAL_ID) AS "COUNT" FROM ANIMAL_OUTS 
  GROUP BY HOUR(DATETIME) HAVING HOUR >= 9 and HOUR < 20
  ORDER BY HOUR(DATETIME);
  ```

15) 입양 시각 구하기(2) (https://programmers.co.kr/learn/courses/30/lessons/59413)

- ```sql
  -- Create a new hour table
  WITH RECURSIVE hours AS (
      SELECT 0 AS HOUR
      UNION ALL
      SELECT HOUR + 1 FROM hours WHERE HOUR < 23
  )
  
  SELECT hours.HOUR, COUNT(ANIMAL_OUTS.ANIMAL_ID) AS "COUNT" FROM hours
  LEFT JOIN ANIMAL_OUTS ON hours.HOUR = HOUR(ANIMAL_OUTS.DATETIME)
  GROUP BY hours.HOUR
  ORDER BY hours.HOUR
  ```

16) 

- 

17)

- 

18)

- 

19)

- 

20)

- 

21)

- 

22)

- 

23)

- 

24)

- 

25)

- 

26)

- 

27)

- 



