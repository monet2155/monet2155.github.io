---
title: "200209 개발일지"
date: 2020-02-09 16:33:30 -0400
categories: Develop
---

T프로젝트를 수정했다.  
Bulb 스크립트를 상속하는 DoorBulb 스크립트가 있다. 지난 개발때 부모클래스의 멤버변수가 자식에 상속이 안 되는 것 같아 다시 한 번 확인해보니 정상적으로 작동했다.  
또한 부모스크립트의 컴포넌트는 삭제해도 정상적으로 작동함을 확인했다.  
- - -  
DoorBulb의 중점은 터치되었을때 오브젝트가 하얀색이면 스테이지가 클리어 되는것이다.  
이를 위해 지난 개발때 완성해둔 DoorBulb 스프라이트들을 GameManager에 public으로 넣었다. 또한, Bulb 클래스에 있던 ChangerBulbImage() 메서드를 virtual로 선언했다.  
- - -  
```c#
    public virtual void ChangeBulbImage()
    {
        gameObject.GetComponentInChildren<SpriteRenderer>().sprite = gameManager.bulbSprites[(int)colorState];
    }
```c#
- - -  

DoorBulb 클래스의 ChangeBulbImage() 메서드는 다음과 같다.  
- - -  
```c#
<pre>
<code>

    public override void ChangeBulbImage()
    {
        gameObject.GetComponentInChildren<SpriteRenderer>().sprite = GameManager.instance.doorBulbSprites[(int)colorState];
    }  
</code>
</pre>  
```
- - -  
이것으로 DoorBulb 의 스프라이트가 정상적으로 변경되었다.  
- - -  
또한, Bulb 클래스의 ActiveBulbAbility() 메서드도 override 했다.  
기존 코드에서는 Bulb 오브젝트 터치시에 CheckWhite() 메서드를 호출했다. 이는 Bulb가 하얀색인지 확인한 후, gameObject.SetActive() 메서드를 사용해 오브젝트를 가렸다.

그러나, 다른 Bulb를 눌렀는데 엉뚱한 하얀 Bulb가 작동되었다. 그래서 Bulb 클래스의 ActiveBulbAbility() 메서드를 virtual로 선언하고, 오브젝트를 가리는 부분을 넣었다. CheckWhite() 메서드에선 ActiveBulbAbility를 호출한다.  
마지막으로 DoorBulb의 ActiveBulbAbility() 메서드에서 scoreText를 Clear!! 라는 텍스트로 수정했다.  
- - -

상속과 override를 매우 간단하게 사용한 개발이었다. 다음은 LockBulb를 제작한다.


- - -  
###### 참고자료: [싱글턴패턴](https://bluemeta.tistory.com/16)