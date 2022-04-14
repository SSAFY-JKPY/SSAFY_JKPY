---
title: "Kruskal Algorithm"
excerpt: "Study for Kruskal Algorithm"
excerpt_separator: "<!--more-->"
author: "CH"
categories:
  - Algorithm
tags:
  - Basic
last_modified_at: 2022-03-16T22:42:00
---

<!--more-->

<br>

## 크루스칼 알고리즘(Kruskal Algorithm)

### 개념

- 최소 비용 간선을 하나씩 추가하며 최소 신장 트리를 만드는 알고리즘.
- 간선을 추가하며 사이클이 발생하는 경우에는 그 간선을 추가하지 않는 방식으로 예외 처리를 한다.
- 알고리즘 과정
  1. 모든 노드들을 초기화. 각 노드는 자신만을 포함하는 그룹에 속하게 된다.
  2. 비용이 가장 작은 간선을 선택한다.
     2-1. 해당 간선에 포함된 노드들이 서로 같은 그룹에 속해 있지 않으면 간선을 추가하고, 두 노드의 그룹을 하나로 합친다.
     2-2. 해당 간선에 포함된 노드들이 같은 그룹에 속해 있다면 사이클을 만들게 되므로 간선을 추가하지 않는다.
  3. 만약 모든 노드들이 하나의 그룹에 속하게 되었다면 반복을 종료하고, 그렇지 않다면 2번 과정을 반복한다.
- 수행 시간은 O(ElogV)이다.
- C++ 예시 코드

```c++
#include <iostream>
#include <vector>
#include <queue>
#include <string>
#include <cstring>
#include <algorithm>
#include <math.h>
#include <cstring>

using namespace std;

struct Edge {
    int from;
    int to;
    int cost;
};

bool cmp(Edge left, Edge right)
{
    return left.cost < right.cost;
}

vector<int> parents; // <- union-find에서 필수적인 배열!!!!!
// parents <- 부모 확인, 조상까지 타고가기 위해

int Find(int x) // x의 조상찾기, 그룹의 소유자(root)
{
    if (x == parents[x]) return x;
    return parents[x] = Find(parents[x]); // Find(parents[x]) : 조상값을 받아오는 역할
}

void Union(int a, int b) // a가 속한 그룹, b가 속한 그룹을 합쳐라!!!
{
    int pa = Find(a);
    int pb = Find(b);
    parents[pa] = pb; // pa가 pb밑으로 들어감. <- 반대의 경우도 상관없음
}

void kruskal()
{
    int n, e;
    cin >> n >> e;
    parents = vector<int>(n + 1);
    for (int i = 0; i <= n; i++)
        parents[i] = i; // 조상판별, 모두가 개별적으로 따로 있다.
    vector<Edge> edge;
    for (int i = 0; i < e; i++)
    {
        int from, to, cost;
        cin >> from >> to >> cost;
        edge.push_back({ from, to, cost });
    }

    // MST, Kruskal
    // 1. cost가 작은 edge부터 확인
    sort(edge.begin(), edge.end(), cmp); // ElogE == ElogN
    int sum = 0; // MST를 구성할때 사용한 총 cost
    for (int i = 0; i < e; i++) // E
    {
        Edge now = edge[i];
        // 2. cylce 판정
        if (Find(now.from) == Find(now.to)) continue; // 같은 그룹이면 무시
        Union(now.from, now.to);
        sum += now.cost;
    }

    cout << sum;
}

int main() {
    kruskal();
}
```
