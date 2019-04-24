# ezquest-ys-db-exam

#### 1. Student(sid, ssn, sname, did) 에서 superkey 를 모두 나열하시오. (20 points.)
<pre>
 sid: student identifier
 ssn: social security number (주민번호에 해당),
 sname: student name, 
 did: department identifier
 -> (sid), (ssn)
    (sid, ssn), (sid, sname), (sid, did), (ssn, sname), (ssn, did)
    (sid, ssn, sname), (sid, ssn, did), (sid, sname, did), (ssn, sname, did)
    (sid, ssn, sname, did)
</pre>

#### 2. Relational algebra 의 six basic operators 를 나열한 후, basic operator 를 사용해서 r ∩ s 를 표현하시오. (15 points)
<pre>
 - select: σ
 - project: π
 - union: U
 - set difference: -
 - cartesian product: x
 - rename: ρ
-> r - (r - s)
</pre>

#### 3. Student(sid, ssn, sname, did) 와 Department(did, dname, budget, building) 에 대해, 다음 SQL query 를 relational algebra 로 표현하시오. (15 points)
<pre>
select	sid, sname
from	Student, Department
where	Student.did = Department.did and dname = ‘CS’
-> πStudent.sid, Student.sname(σStudent.did=Department.did^dname='CS'(Student x Department))
</pre>

#### 4. 다음 schema 를 이용해 각각의 query 를 SQL 문으로 표현하시오. (30 points)
<pre>
Suppliers(sid, sname, address)
Parts(pid, pname, color)
Catalog(sid, pid, cost)

A. Find the pnames of parts for which there is some supplier.
 -> select distinct P.pname
    from Parts P, Catalog C
    where P.pid = C.pid
B. Find the snames of suppliers who supply every part.
 -> select S.sname
    from Suppliers S
    where not exists (
     (select P.pid from Parts P)
     except
     (select C.pid from Catalog C where C.sid = S.sid)
    )
C. For each part, find the sname of the supplier who charges the most for that part.
 -> select P.pid, S.sname
    from Parts P, Suppliers S, Catalog C
    where C.pid = P.pid
    and C.sid = S.sid
    and C.cost = (select max(C1.cost) from Catalog C1 where C1.pid = P.pid)
</pre>

#### 5. Foreign key 정의 시 “on delete cascade” 와 “on delete set null” 의 의미를 example 사용하여 설명하시오. (20 points)
<pre>
 -> on delete cascade: 참조되는 테이블에서 데이터를 삭제하면 참조하는 테이블에서도 삭제됨
 create table UserInfo (
  id varchar(45) not null primary key, 
  name varchar(45) not null)
  
 create table BuyItem (
  user_id varchar(45) not null,
  item varchar(45) not null,
  foreign key(user_id) references UserInfo(id) on delete cascade)
  
 -> on delete set null: 참조되는 테이블에서 데이터를 삭제하면 참조하는 테이블의 데이터는 null로 변경 
 create table BuyItem (
  user_id varchar(45),
  item varchar(45) not null,
  foreign key(user_id) references UserInfo(id)  on delete set null)
  
 insert into UserInfo set id='id1', name='name1'
 insert into UserInfo set id='id2', name='name2'

 insert into BuyItem set user_id='id1', item='item1'
 insert into BuyItem set user_id='id1', item='item2'
 insert into BuyItem set user_id='id2', item='item3'

 delete from UserInfo where id='id1'
</pre>


#### 1. Variable-length records 가 발생하는 이유를 설명하고 slotted page structure 에 대해 기술하시오. (20점)
<pre>
</pre>

#### 2. B+-tree 의 node size 가 2048 bytes, search-key 가 8 bytes, pointer 가 4 bytes 를 차지할 때 다음 질문에 답하시오.
<pre>
A. Root node 의 최소 children 수는 몇 개인가?
 ->
B. Leaf node 가 가질 수 있는 최소 value (search-key) 수는 몇 개인가?
 ->
C. Internal node 가 가질 수 있는 최소 children 수는 몇 개인가?
 ->
</pre>

#### 3. 예제를 사용하여 ACID property 를 설명하시오. (20점)
<pre>
 ->
</pre>

#### 4. 예제를 사용하여 cascading rollback 이 무엇인지를 설명하시오. (20점)
<pre>
 ->
</pre>

#### 5. Checkpoint 가 필요한 이유 및 checkpoint 때 어떤 동작들을 수행하는지를 기술하시오. (20점)
<pre>
 ->
</pre>
