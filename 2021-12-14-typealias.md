# typealias 란?



### 여기서 잠깐 !!!! typealias 가 뭘까??

### typealias - 기존 선언된 데이터 타입에 별칭을 사용함으로써 코드를 더 읽기 쉽도록 만드는 문법입니다

### 예를 들어 typealias Name = String 이라고 한다면

### Name 이라는 타입은 String 을 받는 구나 하고 알수 있습니다

```swift
typealias Name = String

var name: Name = "Jeff"

var nameString: String = "Jeff"

print(name == nameString)

// 출력 결과 :
//		true
```



### 만약 typealias Name = String 이라고 선언하고 

```swift
var num: Name = 3
```

### Int 값을 넣어준다면 아래와 같이 에러가 발생하는 것을 볼 수있습니다.

![image-20211214214529534](/Users/seungchulha/Library/Application Support/typora-user-images/image-20211214214529534.png)

