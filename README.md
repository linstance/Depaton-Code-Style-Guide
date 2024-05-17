# An example of a Depaton code style guide
***
## 어쨰서 코드 스타일이 필요한가

**"규모가 큰 게임은 혼자서 개발할 수 없다"**

많은 개발자들이 알고 있을 보편적인 사실이라고 생각한다
물론 본인이 시간과 능력이 출중한 만능형 개발자라면 말이 달라지겠지만
보편적인 개발자들은 이러한 능력을 갖추고 있지 않다 그렇기 때문에 우리는 협업을 진행한다 
이러한 협업에 과정에서 수많은 개발자가 본인이 담당하는 기능을 개발하거나 남이 개발하던 기능들을 이어서 개발하는 경우가 있다
이러한 경우에 우리는 타인이 작성한 코드를 읽고 분석하는 시간을 가지게 된다 그렇기 때문에
코드의 품질과 가독성을 위하여 우리는 일관된 코드 스타일을 필요로한다 이 문서는 **Depaton Studio**에서 사용하는 코드 스타일에 관련된 가이드를 제공한다.
***
## 형식 지정 규칙
C#에는 두 가지 일반적인 들여쓰기 스타일이 있습니다.

하나는 여는 중괄호를 새 라인에 배치하는 Allman 스타일이고 다른 하나는 여는 중괄호를 이전 헤더와 같은 라인에 배치하는 K&R 스타일 또는 OTB(One True Brace) 스타일'입니다.

**예시(Allman)**
```
void InventoryMouseCursor(bool ShowInventory)
{
    if (!ShowInventory)
    {
        Cursor.lockState = CursorLockMode.Locked;
        Cursor.visible = false
    }
}
```
**예시(K&R)**
```
void InventoryMouseCursor(bool ShowInventory){
    if (!ShowInventory){
        Cursor.lockState = CursorLockMode.Locked;
        Cursor.visible = false
    }
}
```
**Depaton Studio에서는 가독성을 위하여 Allman 스타일을 채택했습니다.**


또한 중첨 if or 중첩 for문에 경우에도 조금더 명확한 표현을 위해서 필수적으로 중괄호를 적용해주세요.


**예시**
```
    if (isDie == true)
    {
        if(score < 10)
        {
            gameOver();
        }
    }
```
***
## 가독성 개선
**공백을 추가하여 코드 밀도 감소:** 추가 공백을 사용하면 라인의 요소들을 시각적으로 분리하는 느낌을 줄 수 있습니다.

**예시**
```
    for (int i = 0; i < 100; i++) { DoSomething(i); }
```


**함수 인수 사이의 쉼표 다음에 하나의 공백을 사용합니다.**

**예시**
```
    CollectItem(myObject, 0, 1);
```


**괄호와 함수 인수 뒤에는 공백을 추가하지 않습니다.**

**예시**
```
    DropPowerUp(myPrefab, 0, 1);
```


**함수 이름과 괄호 사이에 공백을 사용하지 않습니다.**

**예시**
```
    DoSomething()
```


**대괄호 안에 공백을 사용하지 않습니다.**

**예시**
```
    dataArray[index];
```


**흐름 제어 조건 앞에 하나의 공백 사용: 비교 연산자와 괄호 사이에 공백을 추가합니다.**

**예시**
```
    while (x == y)
```

**비교 연산자 앞뒤로 하나의 공백을 사용합니다.**

**예시**
```
    if (x == y)
```

***

## 명명규칙
