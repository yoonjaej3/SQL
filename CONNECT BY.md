## CONNECT BY

 오라클 DB를 사용하면서 순차적으로 SELECT 해오고 싶을때 사용하면 좋은 함수다.
 
 자바를 예로 들경우

 ```
 for(int level;level<10;level++) 
  System.out.printIn(level);
 ```
 
 오라클을 예로 들경우
 
 ```
 SELECT
  lEVEL-1
 FROM DUAL
 CONNECT BY LEVEL<=10
 ```
      
      
