# DISTINCT VS GROUP BY

SELECT DISTINCT depart_no FROM emp

SELECT depart_no FROM emp GROUP BY depart_no

위의 두 쿼리문은 동일결과

GROUP BY는 그룹핑+정렬

DISTNCT는 그룹핑

속도면에서는 DISTINCT가 더좋음.

집계함수가 필요 한 경우에만 GROUP BY를 쓰자

### 집계함수

값에 대하여 특정 연산을 수행하는 함수

SUM

SELECT SUM(salary) FROM employee;

AVG

SELECT AVG(salary) FROM employee;

MIN,MAX

SELECT MIN(salary), MAX(salary) FROM employee;

COUNT

- COUNT는 NULL값을 무시하고 값이 존재하는 데이터에 대한 갯수만 센다

SELECT COUNT(salary), COUNT(commission) FROM employee;

월급이 300만원 이상인 사람들에 대해서 직급별로 2명이상인 직급과 그 직급의 월급 평균을 구해라

SELECT job 직급, AVG(salary) 월급평균 FROM employee

WHERE salary >= 300

GROUP BY job HAVING COUNT(job) >= 2;


# UNION VS UNION ALL
UNION은 두 쿼리의 결과에서 중복되는 값을 삭제하여 나타낸다.

UNION ALL은 두 쿼리의 결과에서 중복되는 값을 모두 보여준다.

속도는 UNION ALL이 더 빠릅니다.

중복체크를 하냐 마냐에 대한 처리 속도 때문

**중복처리 하는 기준**

일반적으로 키, 칼럼 등을 생각할 수 있지만, 모든 컬럼 값들 자체가 중복체크의 기준이 된다.

UNION은 생각보다 속도가 느리기 때문이 많이 사용하지 않는 구문이다.

사용할 필요가 있다면 UNION ALL을 사용하되, 칼럼은 최소한으로 줄여야된다.

SELECT * FROM A

UNION  (ALL)      

SELECT * FROM B




