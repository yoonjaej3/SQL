### **1. NVL 함수 [ NVL( 대상 , null인 경우 값 ) ]**

대상의 값이 NULL 인 경우 지정한 값으로 치환합니다.

모든 데이터 타입에 적용이 가능합니다.

ex ) select **nvl(GOODS_QTY, 0)**  from GOODS;

- > GOODS테이블에 **GOODS_QTY가 null 일 경우 0으로 치환**

### **2. NVL2 함수 [ NVL2( 대상, null 아닌경우 값, null인 경우 값 ) ]**

대상의 값이 **NULL 인 경우**와 **NULL이 아닌경우**를 지정한 값으로 치환합니다.

**NVL2 함수**는 DECODE함수와 비슷한 **IF문의 기능**을 가지고 있습니다.

개인적으로는 DECODE 보다 더 간편하다고 생각하네요.

때에 따라서 NVL2와 DECODE를 사용하시면 될것 같습니다.

ex ) select **NVL2(GOODS_QTY, GOODS_QTY, '재고없음')**  from GOODS;

- > GOODS테이블에 GOODS_QTY가 **NULL이 아닌경우 GOODS_QTY** 으로 치환
- > GOODS테이블에 GOODS_QTY가 **NULL인 경우 '재고없음'** 으로 치환


![image](https://user-images.githubusercontent.com/57666307/124765353-d488d300-df70-11eb-97f4-24d4380e6242.png)
