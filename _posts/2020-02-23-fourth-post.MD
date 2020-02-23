---
title: "200223 개발일지"
date: 2020-02-23 16:24:47 -0400
categories: VSCode Daily C# Unity Develop
---

HDD가 망가졌다. BIOS 세팅에서 S.M.A.R.T 를 끄고 부팅하니 HDD가 아직 인식은 되는 듯 하지만, 읽고 쓰는 부분에서 속도 저하가 엄청났다.  
인식이 될때 최대한 빠르게 프로젝트 몇개를 백업했다. 금방 HDD를 구입하고 설치한 후 공부에 필요한 프로그램 몇가지를 설치했다.

그중 하나가 VS Code이다. 현재 글 작성에도 사용하고 있으며, Git 연동과 Extension들이 굉장히 다양하고 활용성이 좋다.  
나는 글 작성에 필요한 Date를 작성하는게 귀찮아 Insert Date String를 설치했다. Ctrl + Shift + I를 입력하면 다음과 같이 작성해준다.  
2020-02-23 18:08:49
###### [https://stackoverrun.com/ko/q/10686685](https://stackoverrun.com/ko/q/10686685)

---

TurnOnTheLights(TOTL) 프로젝트를 수정하고, Door와 연동되는 Lock과 Key를 추가해 퍼즐게임의 요소를 더했다. 또한, 터치 이벤트시 모든 Bulb의 메서드가 실행되는 경향이 있어 다음과 같이 Hit의 Bulb 컴포넌트만 사용하는 코드를 사용했다.  

```C#
var ray = Camera.main.ScreenPointToRay(Input.mousePosition);
        RaycastHit Hit;

        if (Input.GetMouseButtonDown(0))
        {

            if (Physics.Raycast(ray, out Hit))
            {
                if (Hit.transform.gameObject.TryGetComponent<Bulb>(out Bulb bulb))
                {
                    bulb.CheckWhite();
                }
            }
        }
```

- - -  

Blog에 어느 수준까지 올려야 할지 감이 안 잡힌다. 블로그 운영에 대해 좀 더 진지하게 생각해봐야겠다.