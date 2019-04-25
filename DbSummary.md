
# ezquest-DB Summary

#### 1. Key 개념
<pre>
 - Key는 DB에서 조건에 만족하는 튜플을 찾거나 순서대로 정렬할 때, 다른 튜플들과 구별할 수 있는 유일한 기준이 되는 attribute 속성
  1) 후보키
   - 유일하게 식별할 수 있는 속성들의 부분집합
   - 유일성과 최소성을 만족
  2) 기본키
   - 특정 튜플을 유일하게 구별 할 수 있는 속성
  3) 대체키
   - 후보키가 둘 이상일 때 기본키를 제외한 나머지 후보키들을 말함
  4) 슈퍼키
   - 릴레이션 내에 있는 속성들의 집합으로 구성된 키
   - 유일성은 만족하지만, 최소성은 만족하지 않음
  5) 외래키
   - 참조되는 릴레이션의 기본키와 대응되는 릴레이션 간에 참조 관계를 표현하는데 중요한 도구
</pre>

#### 2. Relational algebra
<pre>
 - select: σ
 - project: π
 - union: U
 - set difference: -
 - cartesian product: x
 - rename: ρ
</pre>

#### 4.View 개념
<pre>
 - 허용된 데이터를 제한적으로 보여주기 위해서 하나 이상의 테이블에서부터 유도된 가상 테이블
</pre>

#### 4. Cursor 개념, Prepared statement
<pre>
 Cursor: 내장 sql문의 수행결과로 반환 될 수 있는 복수의 튜플들을 액세스 할 수 있또록 해주는 개념
  - Declare: 커서를 정의하는 등 커서에 관련된 선언을 하는 명령
  - Open: 커서가 질의 결과의 첫 번째 튜플을 포인트하도록 설정하는 명령
  - Fetch: 질의 결과의 튜플들 중 현재의 다음 튜플로 커서 이동
  - Close: 질의 수행 결과에 대한 처리 종료시 커서를 닫기 위해 사용
 Prepared statement: Statement를 상속받는 인터페이스, sql 구문을 실행시키는 기능을 갖는 객체
</pre>
