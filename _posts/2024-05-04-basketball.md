---
layout: post
title:  "basketball"
date:   2024-05-04 
categories: PYTHON
permalink: /archivers/basketball
---
[문제]: https://www.acmicpc.net/problem/1159
# [문제]
상근이는 농구의 세계에서 점차 영향력을 넓혀가고 있다. 처음에 그는 농구 경기를 좋아하는 사람이었다. 농구에 대한 열정은 그를 막을 수 없었고, 결국 상근이는 농구장을 청소하는 일을 시작했다. 상근이도 농구장을 청소하면서 감독이 되기 위해 가져야할 능력을 공부해나갔다. 서당개 3년이면 풍월을 읊듯이 상근이는 점점 감독으로 한 걸음 다가가고 있었다. 어느 날 그에게 지방의 한 프로농구팀을 감독할 기회가 생기게 되었다. 그는 엄청난 지도력을 보여주며 프로 리그에서 우승을 했고, 이제 국가대표팀의 감독이 되었다.

내일은 일본과 국가대표 친선 경기가 있는 날이다. 상근이는 내일 경기에 나설 선발 명단을 작성해야 한다.

국가대표팀의 감독이 된 이후에 상근이는 매우 게을러졌다. 그는 선수의 이름을 기억하지 못하고, 각 선수의 능력도 알지 못한다. 따라서, 누가 선발인지 기억하기 쉽게 하기 위해 성의 첫 글자가 같은 선수 5명을 선발하려고 한다. 만약, 성의 첫 글자가 같은 선수가 5명보다 적다면, 상근이는 내일 있을 친선 경기를 기권하려고 한다.

상근이는 내일 경기를 위해 뽑을 수 있는 성의 첫 글자를 모두 구해보려고 한다.

# 예제
입력
```
18
babic
keksic
boric
bukic
sarmic
balic
kruzic
hrenovkic
beslic
boksic
krafnic
pecivic
klavirkovic
kukumaric
sunkic
kolacic
kovacic
prijestolonasljednikovi
```
출력
```
bk
```
# 문제풀이
```
N=int(input())
s=''
list=[]
namelist=set()
for i in range(N):
    name=input()
    namelist.add(name[0])
    s+=name[0]
for i in namelist:
    if s.count(i) >= 5:
        list.append(i)
if not list :
    print("PREDAJA")
else:
    print("".join(sorted(list)))
```
입력받을 선수명을 저장할 변수 `N`을 선언하고 `for` 문으로 선수 명수만큼 반복하면서 이름을 입력받고 
`namelist`에는 중복없이 성을 1글자 저장하고 `s`에는 선수들의 성을 모두모아준다.
그다음 `for`문으로 `i`에 중복없이 모은 성을 하나씩대입해주면 모든성을 모은 `s`에 `i`성을 가진사람이 5명보다 많으면`list`에 추가해주고
`if`문으로 `list`값이 비어서 같은성을 가진성수가 5명이안되면 PREDAJA를 `list`에 같은성 가진사람이 있으면 join으로 공백없이 `list`안에 값들을 출력해준다.
