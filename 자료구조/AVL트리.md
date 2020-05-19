## AVL트리
* AVL트리는 트리가 한쪽으로 치우쳐 자라나는 현상을 방지하여 트리 높이의 균형을 유지하는 이진탐색트리
* 균형 이진트리를 만들면 N개의 노드를 가진 트리의 높이가 O(logN)이 되어 탐색,삽입,삭제 연산의 수행시간이 O(logN)으로 보장
* AVL트리는 삽입이나 삭제로 인해 균형이 깨지면 회전 연산을 통해 트리의 균형을 유지한다.

![캡처](https://user-images.githubusercontent.com/54932560/82287901-3a687300-99dc-11ea-8394-552178acccce.PNG)

* [정리] N개의 노드를 가진 AVL 트리의 높이는 O(logN)이다.

### AVL 트리의 회전 연산
* LL,RR,LR,RL 회전 연산이 있다.
* 회전 연산은 2개의 기본적인 연산으로 구현

### LL - 회전
* 노드가 왼쪽(L),왼쪽(L)에 있을때 사용한다.
* 나의 왼쪽자식과 나를 ROTATE_RIGHT 실행 
![캡처](https://user-images.githubusercontent.com/54932560/82324183-335d5700-9a14-11ea-8c7a-9978f74fa4d4.PNG)
![캡처](https://user-images.githubusercontent.com/54932560/82324733-14ab9000-9a15-11ea-9ec7-b7bd737ef2bb.PNG)

### RR - 회전
* 노드가 오른쪽(R),오른쪽(R)에 있을때 사용한다.
- 나의 오른쪽자식과 나를 ROTATE_LEFT 실행.
![캡처](https://user-images.githubusercontent.com/54932560/82325125-a915f280-9a15-11ea-928e-71c1fd40ae60.PNG)

### LR - 회전
* 노드가 왼쪽(L),오른쪽(R)순서로 있을때 사용한다.
* LL모형으로 먼저 만든후 계산한다.
![캡처](https://user-images.githubusercontent.com/54932560/82325388-22ade080-9a16-11ea-96b6-75255000c421.PNG)
![캡처](https://user-images.githubusercontent.com/54932560/82326007-2130e800-9a17-11ea-9b68-4c360ab3b95a.PNG)

### RL - 회전
* 노드가 오른쪽(R),왼쪽(L)순서로 있을때 사용한다.
* RR모형으로 먼저 만든후 계산하다.
![캡처](https://user-images.githubusercontent.com/54932560/82326325-956b8b80-9a17-11ea-8304-88faa91e79d7.PNG)

### 4종류의 회전의 공통점
* 회전 후의 트리들이 모두 동일
- 각 그림(a)의 트리에서 10,20,30이 어디에 위치하든지, 3개의 노드들 중에서 중간값을 가진 노드, 즉 , 20이 위로 이동하면서 10과 30이 작작 20의 좌우 자식이 되기 때문
* 각 회전 연산의 수행시간이 O(1)

### AVL트리가 필요한이유
* 편향(사향) 이진트리가 만들어지면 탐색시간은 최악(순차탐색이랑 같음)
