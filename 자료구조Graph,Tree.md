## Graph

----

### 용어 정의

-----

*그래프*는 관계를 표현하기 위해 필요하고 사용하는 자료구조입니다.이런 그래프는 관계 표현을 위해 *정점(Node, Vertex)*과 *간선(Edge, Link)*을 사용합니다.

- *정점*은 단순히 정보를 담을 수도 있고 상태를 담을 수도 있습니다.
- *간선*은 정보나 상태를 연결합니다. 거리, 비용 등 *가중치(Weight)*를 표시할 수 있습니다.

간선의 연결 상태에 따라서는 다음과 같이 분류할 수 있습니다.

- *무향 그래프*: 방향이 없는 그래프
- *유향 그래프*: 방향이 있는 그래프

그리고 이런 정점과 간선의 관계는 다음과 같은 정의가 있습니다.

- *차수(degree)*: 한 정점에 이어져 있는 간선의 수
  - 입력 차수(indegree): 유향그래프에서 정점으로 들어오는 간선
  - *출력 차수(outdegree)*: 유향그래프에서 정점에서 나가는 간선
- 인접(adjacent): 정점 사이에 간선이 있는 경우

유향그래프중에 cycle이 없는 경우는 DAG(Directed Acyclic Graph)라고 부르는데, 위상정렬 등의 알고리즘에서 사용합니다.

### 구현 및 표현 방법

----

그래프는 필요에 따라 구현 방법이 다르고 다음과 같이 나눌 수  있습니다.

- 인접행렬: N by N 행렬에서 연결 사애를 표시하는 방법
- 인접리스트: 길이 N배열에 각 index별로 연결된 노드만 저장

## Tree

----

### 용어정의

----

트리는 앞서 공부한 Graph중에서도 특정 조건을 만족하는 자료구조입니다.흔히 수학에서도 수형도라는 표현으로 사용하기도 합니다.

트리는 계츨 구조를 가진 데이터에서 많이 사용합니다.가계부, 조직도 등등의 용도가 있습니다.개발에서는 디렉토리 구조, json파일, NoSQL등의 예시도 있습니다.특화된 그래프인만큼 추가적으로 알아둬야 하는 용어들이 있습니다.

가게부와 같이 직접적인 상하관계는 부모와 자식으로 표현합니다.

- *부모노드(Parent node)*: 노드의 직접적인 상위노드
- *자식노드(Child node)*: 노드의 직접적인 하위 노드

부모와 자식이라면 조상과 후손도 있습니다.

- *조상노드(Ancestor node)*: 노드의 부모, 부모의 부모 등 노드의 상위 노드
- *후손노드(Descendant node)*: 노드의 자식, 자식의 자식 등 노드의 하위 노드.

가장 조상인 노드와 가장 후손인 노드,즉 트리의 첫 시작과 끝은 루트노드와 잎노드입니다.

- *root*: 트리의 꼭대기 노드(부모노드 없음)
- *leaf*: 트리의 맨 밑 노드(자식노드 없음)

그리고 root와 거리를 깊이(deth, level)라고 합니다.

그리고 트리도 그래프와 마찬가지로 부분 트리를 가질 수 있습니다.상단히 재귀적인 모습을 띄고 있으며 *subtree*라는 표현을 사용합니다.

이런 트리는 항상 부모노두는 루트를 제외하고 1개입니다.자식의 수는 정해지지 않았습니다.그 중에서도 자식 수를 2개로 제한하는 *이진트리(Binary Tree)* 가 있습니다. 이런 이진트리도 상태에 따라 몇 가지 명칭이 있습니다.

- 포화 이진 트리(Full Binary Tree): 모든 레벨이 꽉 찬 트리
- 완전 이진 트리(Complete Binary Tree): 위에서 아래, 왼쪽에서 오른쪽으로 차근차근 쌓인 트리

### 구현 및 표현 방법

-----

- *부모를 저장하는 방식*: 트리는 부모노드가 0 또는 1개임을 이용하여 1차원 배열에 저장하는 방법입니다.
- *자식을 저장하는 방법*: 이진 인접리스트와 동일합니다.

각각의 장단점이 있습니다.부모를 저장하는 방식은 메모리가 절약되지만, 아래로 순회를 돌기에는 비교적 어렵습니다.하지만 부모만 저장되어 있으면 재귀적으로 조상까지 접근이 가능한 장점이 있습니다.자식을 저장하는 방식은 아래로 순회할 때, 편리합니다.

## 트리 기반 자료구조

----

### 힙(Heap)

-----

*우선순위 큐(Priority Queue*는 본인이 정한 *우선순위*대로 `pop`할 수 있는 Queue를 의미합니다.여기서 우선순위는 수의 대소관계, tuple의 대소관계 등이 될 수 있습니다.

매순간 정렬을 하여 원하는 값을 얻는 방식은 매우 비효율적이기에 조금 특별한 방식을 사용합니다.바로 맨 위 노드인 *루트*만 신경쓰는 방식입니다.

*heapq*라이브러리를 사용하면 됩니다.

- `heappush`: 원소를 넣는 연산
- `heappop`: root원소를 빼는 연산
- `heapify`: 리스트를 heap으로 변환

### 이진탐색트리(BST, Binary Search Tree)

-----

이진트리를 활용하면 *탐색(Search)*을 쉽게 할 수 있습니다.

이진 트리는 자식노드를 left와 right로 나눌 수 있습니다.그렇다면 기존 노드보다 작은 값을 left에 오른쪽 값을 right로 둔다면 정리체계가 확실하지 않을까요?

### Etc

-----

그 외에도 다음과 같은 자료구조가 존재합니다.이진 탐색 트리의 문제인 불균형성을 해결하기 위한 BBTS(Balanced Binary Search Tree)입니다.Balance Factor이라는 개념이 포함되어 있습니다.

- AVL Tree
- 2-3-4 Tree
- Splay Tree
- Red-Black Tree

