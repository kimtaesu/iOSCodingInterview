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

### 18- What is the difference between BDD and TDD?
BDD는 엔지니어가 아닌 사람들이 읽을 수 있음

### 24- What is bitcode ?
비트 코드는 iTunes Connect로 전송되는 'LLVM Bitcode'코드 유형을 나타냅니다. 이를 통해 Apple은 특정 계산을 사용하여 앱을 다시 최적화 할 수 있습니다 (예 : 가능한 경우 실행 파일 크기 축소). Apple이 실행 파일을 변경해야한다면 새로운 빌드를 업로드하지 않고도이 작업을 수행 할 수 있습니다.

iTunes Connect에 업로드하는 앱은 App Store에서 컴파일되고 연결됩니다. 비트 코드를 포함 시키면 애플이 새로운 버전의 앱을 스토어에 제출할 필요없이 애플이 앱 바이너리를 나중에 다시 최적화 할 수있게된다.

### 1- Please explain Method Swizzling in Swift

### 33- What is the difference between a delegate and an NSNotification?
1:1 Delegate
1:N NSNotification

### 37- Explain View Controller Lifecycle events order?
- loadView
> ViewController 가 View 를 생성
- viewDidLoad
> ViewController의 View가 메모리에 로드 된 후에 호출됩니다
- viewWillAppear
> View가 화면에 표시 될 때마다 호출됩니다.
- viewWillLayoutSubviews
> ViewController의 View가 SubView의 Layout을 업데이트 할때 호출된디. 
이 메소드는 Frame이 변경 될 때마다 호출됩니다.
- viewDidLayoutSubviews
> ViewController가 SubView를 방금 배치했음을 알리기 위해 호출됩니다.
- viewDidAppear
> ViewController에 View가 View 계층에 추가되었음을 알립니다.
- viewWillDisappear
>  ViewController가 화면에서 제거되기 전에이 메소드가 호출됩니다.
- viewDidDisappear
> ViewController가 화면에서 제거되면 메서드가 호출됩니다.
- viewWillTransition
> 뷰의 사이즈가 변경되는 것을 컨테이너에 통지합니다.

##### Parent -> Child -> Parent 

1. Parent: viewDidLoad
2. Parent: viewWillAppear
3. Parent: viewWillLayoutSubviews
4. Parent: viewDidLayoutSubviews
5. Parent: viewDidAppear
6. Child: viewDidLoad
7. Parent: viewWillDisappear
8. Child: viewWillAppear
9. Child: viewWillLayoutSubviews
10. Child: viewDidLayoutSubviews
11. Parent: viewDidDisappear
12. Child: viewDidAppear
13. Child: viewWillDisappear
14. Parent: viewWillAppear
15. Child: viewDidDisappear
16. Parent: viewDidAppear

###### Parent Rotate
1. Parent: viewWillTransition
2. Parent: viewWillLayoutSubviews
3. Parent: viewDidLayoutSubviews
4. Parent: viewWillLayoutSubviews
5. Parent: viewDidLayoutSubviews
