---
title: "200207 개발일지"
date: 2020-02-07 20:57:00 -0400
categories: Develop Design
---

안드로이드 대수 프로젝트를 수정했다.  
좌 우 터치를 인식해 10의 지수가 작아지고 커지는 코드를 추가했다.  
화면의 크기를 받아오는 코드는 다음과 같다.

---
<pre>
<code>
Display display = getWindowManager().getDefaultDisplay();  
int width = display.getWidth();  
int height = display.getHeight();  
</code>
</pre>

- - -

화면의 크기를 받아온 후에는 Width를 반으로 나눈 값을 중간 픽셀값으로 저장하고, 터치이벤트에서 얻은 RawX값과 비교하면 된다.  
지킬에서 코드블럭을 사용하는 부분을 더 알아봐야겠다.  

------  


다음으로 TurnOnTheLights 프로젝트의 DoorBulb 오브젝트용 스프라이트를 만들었다.  

![GreenDoor](/assets/images/GreenDoor.png){: width="20%" height="20%"}


지금보니까 생각보다 구려보이는 듯 하다.  
또한 DoorBulb 스크립트를 어느정도 작성했는데, 클래스 상속과 관련해 여러가지 수정해야 할 부분이 많다. 조만간 또 수정해야겠다.