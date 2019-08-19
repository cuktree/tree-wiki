# B-Tree

## 개요

- 자식 노드의 개수가 2개 이상인 트리
- 노드 내의 데이터가 1개 이상일 수 있다.
- 노드 내 최대 데이터 수가 2개라면 2차 B-Tree, 3개라면 3차 B-Tree라고 한다.
- 차구사 짝수인지 홀수인지에 따라 알고리즘이 많이 달라진다.



## 특성

- 노드의 데이터수가 n개라면 자식 노드의 개수는 n+1
- 노드의 데이터는 반드시 정렬된 상태여야 한ㅋ다.
- 모든 leaf 노드들은 같은 level에 있어야 한다.
- leaf 노드들은 최소 tree의 degree의 [m/2]-1개의 key를 가지고 있어야 한다.(???)



## 탐색



## 삽입

node의 overflow가 발생되면 (key==M) 노드의 t-1 번째 key를 parent로 올리고 노드 분할을 한다.

- 차수가 홀수이면 가운데 값, 짝수이면 절반으로 나눴을 때 왼쪽 그룹의 최대값

[참고자료] https://potatoggg.tistory.com/174



## 삭제

- 삭제를 하기 위해서 leaf node로 해당 원소를 이동시켜야 한다.
- 삭제를 위한 하향 탐색을 하면서 자료수가 m/2이하인 노드는 형제에게 빌리든지 결합해야함.



## 특성

- m차 b-tree 높이는 
  $$
  log_{M/2}N
  $$

- 검색시 각 노드당 최대 M번의 순차 검색

- 삽입/삭제/검색 성능

  - <img src="https://latex.codecogs.com/svg.latex?\Large&space;x=c*M*log_{m/2}N" title="\Large x=c*M*log_{m/2}N" />

  - $$
    T(n)<c*M*log_{m/2}N,\ 즉\ O(logN)의\ 성능
    $$

    

---

참고 

- https://hyungjoon6876.github.io/jlog/2018/07/20/btree.html
- https://potatoggg.tistory.com/174