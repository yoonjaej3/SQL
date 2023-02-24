# LOCK 해제

## 1. 락이 걸린 테이블 찾기
```
SELECT  DO.OBJECT_NAME
      , DO.OWNER
      , DO.OBJECT_TYPE
      , VO.XIDUSN
      , VO.SESSION_ID
      , VO.LOCKED_MODE
   FROM V$LOCKED_OBJECT VO
      , DBA_OBJECTS DO
  WHERE VO.OBJECT_ID = DO.OBJECT_ID;
  
  ```
  
  
## 2. 해당 sid 와 serial 번호 구하기 - 테이블별 확인

```
SELECT A.SID, A.SERIAL#
  FROM V$SESSION A
     , V$LOCK B
     , DBA_OBJECTS C
 WHERE A.SID         = B.SID
   AND B.ID1         = C.OBJECT_ID
   AND B.TYPE        = 'TM'
   AND C.OBJECT_NAME = '테이블명';
```

## 3. sid 와 시리얼 번호로 세션 해제 ( 세션 KILL )
```
ALTER system kill session '248, 23259';
```

