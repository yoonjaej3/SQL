# DISTINCT VS GROUP BY

**SELECT DISTINCT depart_no FROM emp**

**SELECT depart_no FROM emp GROUP BY depart_no**

위의 두 쿼리문은 동일결과

GROUP BY는 그룹핑+정렬

DISTNCT는 그룹핑

속도면에서는 DISTINCT가 더좋음.

집계함수가 필요 한 경우에만 GROUP BY를 쓰자

### 집계함수

값에 대하여 특정 연산을 수행하는 함수

SUM

**SELECT SUM(salary) FROM employee;**

AVG

**SELECT AVG(salary) FROM employee;**

MIN,MAX

**SELECT MIN(salary), MAX(salary) FROM employee;**

COUNT

- COUNT는 NULL값을 무시하고 값이 존재하는 데이터에 대한 갯수만 센다

**SELECT COUNT(salary), COUNT(commission) FROM employee;**

월급이 300만원 이상인 사람들에 대해서 직급별로 2명이상인 직급과 그 직급의 월급 평균을 구해라

**SELECT job 직급, AVG(salary) 월급평균 FROM employee**

**WHERE salary >= 300**

**GROUP BY job HAVING COUNT(job) >= 2;**
