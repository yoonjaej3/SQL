## 오라클 Pivot 문법 


### 테이블의 행을 열로(PIVOT), 열을 행으로(UNPIVOT) 변환 


#### 1) 부서별, 직책별 그룹화로 최고 급여 데이터 출력
```
SELECT DEPTNO, JOB, MAX(SAL)
FROM EMP
GROUP BY DEPTNO, JOB
ORDER BY DEPTNO, JOB
```

![image](https://user-images.githubusercontent.com/57666307/177681488-d28ecd39-fc23-4ac0-89e4-ad3943ff87a0.png)

#### 2) PIVOT 함수. 직책별, 부서별 최고 급여를 2차원 표로 출력
```
SELECT *
FROM (
    SELECT DEPTNO, JOB, SAL
    FROM EMP
)
PIVOT ( MAX(SAL) FOR DEPTNO IN (10, 20, 30) )
ORDER BY JOB;
```

![image](https://user-images.githubusercontent.com/57666307/177681595-9798c29d-a0d4-4ab3-bec0-33f84294caf4.png)





출처: https://yzink.tistory.com/45 [양디로그:티스토리]
