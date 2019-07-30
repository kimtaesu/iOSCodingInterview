### 4- What is made up of NSError object? 
* a domain, 
* an error code
* user info dictionary

### 8- What is @synthesize in Objective-C? 
Synthesize는 속성에 대한 getter 및 setter 메서드를 생성합니다.

### 9- What is @dynamic in Objective-C? 
@dynamic은 getter와 setter가 다른 곳에서 구현된다는 것을 컴파일러에게 알려줍니다.

### 17- What is Responder Chain ? 
ResponderChain은받은 이벤트에 응답 할 수있는 개체의 계층 구조입니다.

### 5- Explain #keyPath() ?
keyPath ()를 사용하면 StaticString 또는 StringLiteralConvertible로 사용되는 키 경로 리터럴 문자열을 사용하여 정적 유형 검사가 수행됩니다.

### 15- What is the difference open & public access level?
> Open은 다른 모듈이 클래스를 사용하고 클래스를 상속 할 수있게합니다. 구성원에 대해 다른 모듈이 구성원을 사용하여이를 대체 할 수있게합니다.

> Public은 다른 모듈이 public 클래스와 public 멤버 만 사용할 수있게합니다. 
공용 클래스를 더 이상 서브 클래 싱 할 수 없으며 공용 멤버를 재정의 할 수도 없습니다.

[Sample](https://github.com/kimtaesu/MyPlayGround/blob/master/AccessLevel.playground/Contents.swift)

### 16- What is the difference fileprivate, private and public private(set) access level ?
`fileprivate`는 현재 파일 내에서 액세스 할 수 있으며 `private`은 현재 선언 내에서 액세스 할 수 있습니다.

`public private (set)`은 getter가 public이지만 setter가 private임을 의미합니다.

[Sample](https://github.com/kimtaesu/MyPlayGround/blob/master/FilePrivateVPrivate.playground/Contents.swift)
