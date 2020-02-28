---
title: "200228 개발일지"
date: 2020-02-28 18:39:16 -0400
categories: C# Unity Develop
---

새로운 게임 프로젝트를 시작했다.  
학교 전공 수업용 팀 프로젝트이며 나는 프로토타입으로 게임 씬 한 개를 만든다.  

- - -  

개발 중 다음 에러가 발생했다. 
![Inspectorerror](/assets/images/Inspector_error.jpg){: width="60%" height="60%"}  
SerializedObjectNotCreatableException : Object at index 0 is null  
구글링 결과 Inspector창이 여러개일 경우에 발생하며, 창을 닫았다가 몇 초 후에 열면 사라진다고 하지만, 작동하지 않아 유니티 에디터 자체를 끄니 정상적으로 사라졌다.  

- - -  

Collider를 사용해 Trigger 이벤트를 받아오는 과정에서 Trigger 충돌이 발생하지 않아 애를 먹었다. 이는 둘 중 한쪽이라도 RigidBody가 없어 일어났다. 한 쪽에 컴포넌트를 추가해 해결했다.  
###### [http://blog.naver.com/PostView.nhn?blogId=dj3630&logNo=221454886465](http://blog.naver.com/PostView.nhn?blogId=dj3630&logNo=221454886465)  


- - -  


프로젝트 T에서는 사용하지 않던 Collider, Animator, NavMeshAgent를 사용하니 17년도 전공시간에 배웠던 지식을 다시 꺼내보고 반성하는 계기가 됐다. 사소한 것에서 헤매고 구글링 하다 보니 그 때의 학구열이 다시 떠올랐다. 열심히 해야겠다.