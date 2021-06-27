# LIKE

**시작 문자 검색하기**

SELECT FIRST_NAME, LAST_NAME

FROM EMPLOYEES

WHERE FIRST_NAME LIKE 'A%'



**끝에 문자열 검색하기**

SELECT FIRST_NAME, LAST_NAME

FROM EMPLOYEES

where UPPER(FIRST_NAME) like '%NA'



**특정 위치부터 검색하기(3번째 문자가 a인 상황)**

SELECT first_name, last_name

FROM employees

WHERE last_name LIKE '__a%'



**AND조건으로 검색하기 ( 두 문자열 모두 가지고 있을 경우)**

SELECT last_name

FROM employees

WHERE last_name LIKE '%a%' and last_name LIKE '%e%'



**특정 위치에 여러개의 문자가 해당하는 경우 추출**
SELECT last_name

FROM employees

where substr(last_name, 1, 1) in ( 'a', 'b', 'c', 'd', 'e')

→ 함수 : SUBSTR("문자열", "시작위치", "길이")



**[EXCAPE] %나 _ 가 들어갔는지 검색하고 싶을경우**

select JOB_ID

from employees

where JOB_ID like '%#___' ESCAPE '#';
