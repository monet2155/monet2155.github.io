---
title: "200207 개발일지"
date: 2020-02-07 20:57:00 -0400
categories: Develop Design
---

대수 프로젝트를 수정했다.  
좌 우 터치를 인식해 10의 지수가 작아지고 커지는 코드를 추가했다.  
화면의 크기를 받아오는 코드는 다음과 같다.

<pre>
<code>
Display display = getWindowManager().getDefaultDisplay();
int width = display.getWidth();
int height = display.getHeight();
</code>
</pre>

