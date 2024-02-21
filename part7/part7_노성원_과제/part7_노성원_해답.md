## Q1. SQL명령어 중 DROP과 DELETE의 차이는 무엇인가요?
DROP은 DDL명령어로 테이블 자체를 완전히 없애버리는 방식으로 모두 삭제되므로 사용에 주의해야한다. 자동 COMMIT되는 명령어 이므로 되돌릴 수 없다. 
DELETE는 DML명령어로 튜플을 삭제하는데 이는 데이터를 하나씩 선택하여 제거하는 방식이다. COMMIT전이면 ROLLBACK으로 되돌릴 수 있다. 원하는 데이터를 골라서 삭제할 때 사용한다.

## Q2. primary key에 대해 설명하시오
primary key는 후보키 중 하나를 선정하여 대표로 선정된 키이다. 테이블의 모든 행에는 기본 키가 있어야하며 각각 unique한 값을 가지므로 서로 다른 행은 동일한 기본 키를 가질 수 없다. 기본 키 값은 절대로 null이거나 변동될 수 없다.

## Q3. 개념적 모델링에서 정의된 entity, attribute, relation이 논리적 모델링에서 의미하는 것은 무엇인가요?
논리적 모델링은 데이터 모델을 구현하기 위해 형식을 정리하는 과정이다.
entity는 테이블 or 리스트 형식, attribute는 column or 리스트의 원소, relation는 primary key, foreign key 등을 나타낸다.
