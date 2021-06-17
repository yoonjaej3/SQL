## IF

일반 IF 문과 비슷.

값이 빈 값이 아닐때 조회 조건에 추가하는 경우 사용.

```

 select * from T_TEST T
 where T.ID = 'id'
 <if test="name != null and name != ''">
    and T.NAME = #{name}
 </if>
```

## Choose

자바에서 사용하는 switch 문과 비슷.
choose 태그 내에서 when , otherwise 태그 사용.
when 조건과 일치하면 해당 쿼리문을, 일치하는 것이 없으면 otherwise 태그의 쿼리문을 추가

```

   select * from T_TEST T 
   where T.ID = 'id'
   <choose>
      <when test="period > 20">
          and T.PERIOD > #{period}
      </when>

      <when test="period < 20">
          and T.PERIOD < #{period}
      </when>

      <otherwise>
          and T.PERIOD = 20
      </otherwise>
   </choose>

```
