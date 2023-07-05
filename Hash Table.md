# Hash Table

효율적인 탐색을 위한 자료구조로써 key-value 쌍의 데이터를 입력받음, key 값을 입력으로 얻은 해시값을 위치로 지정하여 key-value 데이터 쌍을 저장

저장, 삭제, 검색 모두 O(1)

구현 방법
- **Array List based**
- Array List + Linked List based

<-> Direct Address Table: key값이 인덱스가 되는 테이블 - key 값이 크거나 문자열로 들어올 경우 저장하기 쉽지 않음

* Hash Table 의 문제점  
이미 데이터를 가진 위치에 또 값이 들어올 경우   
해결 방법) Open addressing: 값이 없을 때까지 인덱스를 계속 이동 - 시간복잡도 O(1)

=> **Dictionary 이용**

dictionary의 in 연산 - O(1)
<-> List의 in 연산 - O(n)
