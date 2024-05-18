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

## 대소문자 사용
Depaton Studio에서 사용되는 표기법은 크게 두가지가 있습니다.

첫 번째는 파스칼 표기법입니다. 쌍봉낙타 표기법이라고도 불리는 파스칼 표기법은 무조건 대문자로 시작해서 중간에 특수문자나 공백없이 작성되며 모든 단어의 시작은 대문자로 작성됩니다.

**예시**
```
public float PlayerExp;
public int PlayerHp;
public int PlayerMp;
```
두 번째는 카멜 표기법입니다. 단봉낙타 표기법이라고도 불리는 카멜 표기법은 무조건 소문자로 시작해서 공백이나 특수문자 없이 작성하며 이어지는 단어의 경우에는 앞 글자를 대문자로 작성합니다.

**예시**
```
public float playerExp;
public int playerHp;
public int playerMp;
```
Depaton Studio에서는 public 필드, 열거형, 클래스, 메서드에 파스칼 표기법을, private 변수에는 카멜 표기법을 사용하고 있습니다.

## 명명 규칙
변수는 일반적으로 상태를 나타내고 있으므로 보다 명확한 표현을 위해서 구체적인 명사를 사용하여 이름을 나타내 주는 것이 좋습니다.

또한 true나 false 값을 나타내는 변수에 대해서는 bool을 접두사로 사용해 주세요. 일반적으로 bool을 접두사로 사용하는 변수의 경우에는
플레이어가 현재 뛰고 있는지 게임이 클리어되었는지 아니면 현재 플레이가 사망했는지 질문하는 형태로 true or false를 반환하는 경우가 많을 것입니다. 
이러한 변수에 경우에는 동사를 사용해서 isPlayerDead, isWalking, isClear와 같은 형태로 변수 이름을 확실하게 명명해 주세요.

메서드는 작업을 수행하기 때문에 이름을 동사로 시작하고 반환 유형을 기반으로 필요에 따라 컨텍스트를 추가하여 GetDirection, FindTarget 등과 같이 사용해 주세요.
메서드의 반환 유형이 bool 이라면 위와 같은 형식으로 예를 들어 IsGameOver, HasStartedTurn 등의 질문 형식이 표현해 주시면 됩니다.

이벤트와 이벤트 핸들의 명명에도 몇 가지 규칙이 있습니다. 이벤트의 이름을 메서드와 비슷하게 동사 구문으로 해주세요. 상태 변경을 정확하게 전달할 수 있는 이름을 사용하는 것이 좋습니다. 또한 현재분사나 과거분사를 사용하여 '이전' 또는 '이후' 이벤트를 나타냅니다. 예를 들어 문을 열기 전의 이벤트를 OpeningDoor라고 하고 문을 연 이후의 이벤트에 DoorOpened라는 이름을 사용합니다.

한 줄에 한 개의 변수만을 선언해 주세요. 줄수를 줄인다고 해서 가독성이 좋아지거나 하지 않습니다.

인터페이스 이름에는 대문자 'I'를 접두사로 사용하고 그 뒤에 기능을 설명하는 형용사를 붙여 주세요. 이벤트 발생 메서드(주체)에 'On' 접두사를 사용해주세요. 이벤트를 발생시키는 주체는 일반적으로 'On' 접두사가 있는 메서드(예: OnOpeningDoor, OnDoorOpened)에서 이벤트를 호출합니다.

**예시**
```
public interface IDamageable<T>
{
    void Damage(T damageTaken);
}

public void OnDoorOpened()
{
    DoorOpened?.Invoke();
}
```

함수나 메서드를 선언 시 서로다른 함수와 메서드 사이에 한 줄 정도 공백을 넣어 주세요.

**예시**
```
public void RandomItem()
{
    Random();
}

public void RandomMonster()
{
    MonsterSpawn();
}
```
