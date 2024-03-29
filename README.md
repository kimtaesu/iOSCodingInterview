## [50 iOS Interview Questions And Answers](https://medium.com/@duruldalkanat/ios-interview-questions-13840247a57a)
Part 1,2,3,4,5 에서 잘 모르는 부분을 정리하였습니다.

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

### 38- What is the difference between LLVM and Clang?
프런트 엔드 (Clang)는 소스 코드를 가져 와서 추상 구문 트리 (LLVM IR)를 생성합니다.


### 42- When and why do we use an object as opposed to a struct?
Structs: value type
Classes: reference type

### Content Hugging & Compression Resistance
1. Content Hugging은 고유 사이즈의 최대 크기에 제한을 두는 것입니다
> Hugging의 우선순위 1000이 제약의 우선순위 900보다 크므로 레이블의 크기는 최대 108보다 커지지 않게 됩니다.
2. Compression Resistance는 최소 크기에 제한을 두는 것입니다.
> Resistance의 우선순위 1000이 제약의 우선순위 900보다 크므로 너비의 고유 값인 108보다 작아지지 않게 됩니다.

### iOS 앱의 상태는 무엇입니까?
1. *Non-running*: not running
2. *Inactive*: 앱이 포 그라운드에서 실행 중이지만 이벤트를받지 못했습니다. 예를 들어 통화 또는 SMS 메시지를받을 때 비활성 상태로 설정할 수 있습니다.
3. *Active*: 앱이 포 그라운드에서 실행되고 이벤트를 수신 중입니다.
4. *Background*: 앱이 백그라운드에서 실행되고 코드가 실행 중입니다.
5. *Suspended*: 앱이 백그라운드에 있지만 코드가 실행되고 있지 않습니다.

application(_:didFinishLaunching:) - 앱이 처음 시작될 때 실행

applicationWillResignActive: - 앱이 active 에서 inactive로 이동될 때 실행 

applicationDidEnterBackground: - 앱이 background 상태일 때 실행 

applicationWillEnterForeground: - 앱이 background에서 foreground로 이동 될때 실행 (아직 foreground에서 실행중이진 않음)

applicationDidBecomeActive: - 앱이 active상태가 되어 실행 중일 때

applicationWillTerminate: - 앱이 종료될 때 실행

### 2- What kind of JSONSerialization have ReadingOptions?
1. *mutableContainers*: arrays and dictionaries 이 상수가 아닌 변수 객체로 만들어 지도록 지정합니다.
2. *mutableLeaves*: JSON 객체 그래프의 리프 문자열을 variable String의 인스턴스로 생성하도록 지정합니다.
3. *allowFragments*: 파서가 Array 또는 Dictionary의 인스턴스가 아닌 최상위 수준의 객체를 허용하도록 지정합니다.

### 4- What is DispatchGroup?
[Sample](https://github.com/kimtaesu/MyPlayGround/blob/master/DispatchGroup.playground/Contents.swift)
DispatchGroup은 작업의 집계 동기화를 허용합니다. 여러 대기열에서 실행될 수도 있지만 여러 작업 항목을 제출하고 작업이 완료되면 추적 할 수 있습니다. 이 작업은 지정된 모든 작업이 완료 될 때까지 진행할 수 없을 때 도움이 될 수 있습니다.

### 7- Please explain types of notifications.
원격 및 로컬: 원격 알림을 사용하려면 서버에 연결해야합니다. 
로컬 알림: 로컬 알림은 기기에서 발생합니다.

### 11- What is the difference ANY and ANYOBJECT ?
1. Any: func 및 optional을 포함하여 모든 유형의 인스턴스를 나타낼 수 있습니다.
2. AnyObject: 모든 클래스 유형의 인스턴스를 나타낼 수 있습니다.

### 24- What’s the difference optional between nil and .None?
다른 점이 없다. 

### 39- Explain the difference between atomic and nonatomic synthesized properties
1. atomic : 기본 동작입니다. 오브젝트가 원자 적으로 선언되면 스레드로부터 안전합니다. thread-safe는, 그 클래스의 특정의 인스턴스의 1 개의 thread 만, 그 객체를 제어 할 수있는 것을 의미합니다.
2. nonatomic : 스레드로부터 안전하지 않습니다. 비 원자 속성 속성을 사용하여 합성 된 접근자가 단순히 값을 직접 설정하거나 반환하도록 지정할 수 있습니다.이 경우 동일한 값이 다른 스레드에서 동시에 액세스되는 경우 어떤 일이 발생하는지 보장하지 않습니다. 이러한 이유 때문에 원자가 아닌 속성에 액세스하는 것이 더 빠릅니다.


### 19- What is intrinsic content size?
자체 콘텐츠 크기

### 32- KVO VS NotificationCenter ?
KVO와 NotificationCenter의 가장 큰 차이점은 KVO가 특정 개체에 대한 특정 변경 사항을 추적하는 반면 NotificationCenter는 일반 이벤트를 추적하는 데 있습니다.

### 49- What’s the difference between a xib and a storyboard?
1. xib는 하나의 View 또는 View Controller 화면을 정의
2. Storyboard는 많은 View Controller를 보여주고 그 사이의 관계를 보여줍니다.

### 11- What is difference Layout Margins and Directional Layout Margins?
1. Layout Margins 속성은 UIEdgeInsets 유형이며 뷰의 프레임에 적용될 때 뷰의 여백을 정의하는 위쪽, 왼쪽, 아래쪽 및 오른쪽 Inset를 정의합니다.
2. Directional Layout Right-To-Left (RTL) 언어를 인식하는 여백. 레이아웃 앵커로 제약 조건을 만들 때 사용되는 패턴을 따릅니다.

### 15- Explain rethrows keyword
rethrows 키워드는 외부 함수가 전달 된 클로저가 현재 범위로 전달되는 오류를 throw하는 경우에만 throwing 함수임을 컴파일러에 나타냅니다.

### 16- Explain @objc inference
@objc로 Swift 선언에 태그를 추가하여 Objective-C에서 사용할 수 있음을 나타낼 수 있습니다

### 19- Explain Content offset
![](http://appleharikyu.jp/iphone/wp-content/uploads/2018/07/UIScroll%E3%81%AE%E3%83%95%E3%82%9A%E3%83%AD%E3%83%8F%E3%82%9A%E3%83%86%E3%82%A3.png)

### 24- What is the difference between Array vs NSArray ?
1. Array 한 가지 유형의 데이터 만 저장
2. NSArray는 다른 유형의 데이터를 보유 할 수 있습니다. NSArray 불변의 참조 형식입니다.

### copy vs retain?
1. retain: 을 호출하면 보유 수는 1만큼 증가합니다. 목표의 보유 수가 0에 도달하면 오브젝트가 할당 해제되고 메모리에서 해제됩니다.
2. copy: 해당 오브젝트의 복제본이 작성됩니다.

### NSObject -> UIButton 설명
UIButton -> UIControl -> UIView -> UIResponder -> NSObject

### indirect keyword
다음과 같은 재귀 열거 사례를 허용하는 간접 키워드입니다.
```
enum List<T> {
  indirect case node(T, List<T>)
}
```

### Operation VS GCD 
Operation and OperationQueue는 GCD 위에 구축됩니다.

* GCD: 스케줄하지 않습니다. 시스템이 일정을 관리합니다
* Operation: GCD에 비해 약간의 오버헤드가 추가되지만 작업간의 종속성을 추가하고 다시 사용, 취소 일시 중단을 할 수 있습니다.


### Process VS Thread
#### Process
프로세스는 실행 중인 프로그램으로 디스크로부터 메모리에 적재되어 CPU 의 할당을 받을 수 있는 것을 말한다. 운영체제로부터 주소 공간, 파일, 메모리 등을 할당받으며 이것들을 총칭하여 프로세스라고 한다.

#### Thread 
한 프로세스 내에서 동작되는 여러 실행 흐름으로 프로세스 내의 주소 공간이나 자원을 공유할 수 있다.

### iOS 13
1. 다크모드
2. 애플 로그인

### AssociationPolicy
* OBJC_ASSOCIATION_ASSIGN: 추가된 객체와 약한 참조
* OBJC_ASSOCIATION_RETAIN_NONATOMIC: 추가된 객체와 강력 참조 및 nonatomatic으로 설정
* OBJC_ASSOCIATION_COPY_NONATOMIC: 추가된 객체를 복사 및 nonatomatic으로 설정
* OBJC_ASSOCIATION_RETAIN: 추가된 객체와 강력 참조 및 atomatic으로 설정
* OBJC_ASSOCIATION_COPY: 추가된 객체를 복사 및 atomatic으로 설정

### CoreData vs Sqlite
[여기](https://www.letmecompile.com/%EC%BD%94%EC%96%B4%EB%8D%B0%EC%9D%B4%ED%84%B0core-data%EC%99%80-%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%B2%A0%EC%9D%B4%EC%8A%A4%EC%9D%98-%EC%B0%A8%EC%9D%B4/)

### DispatchQueue QoS
1. userInteractive 
2. userInitiated 
3. default 
4. utility 
5. background 
6. unspecified

### viewDidLayoutSubviews vs viewWillLayoutSubviews
각 이벤트에서 무엇을 수행하면 좋을지? 
[stackoverflow](https://stackoverflow.com/questions/23457391/when-are-the-viewwilllayoutsubviews-and-viewdidlayoutsubviews-methods-called)

###### viewWillLayoutSubviews
* View Load, 회전 이벤트, 또는 자식 뷰 컨트롤러의 크기가 부모에 의해 변경 될 때 발생합니다
* 업데이트하기 전에 업데이트 해야하는 것이 있으면 여기에서 수행해야합니다.
> 제약 조건을 업데이트하면 다른 레이아웃 패스가 발생할 수 있으므로 일반적으로 여기서 **제약 조건을 업데이트하지 않아야**합니다.

###### viewDidLayoutSubviews
모든 하위 뷰가 배치되면 호출됩니다.

### Viewwillappear vs ViewDidappear
각 이벤트에서 무엇을 수행하면 좋을지? 
[stackoverflow](https://stackoverflow.com/questions/5630649/what-is-the-difference-between-viewwillappear-and-viewdidappear)
###### ViewWillAppear
View가 나타나기 전이기 때문에 **무거운 작업이 있으면 안됨**

###### ViewDidAppear
실행 시간이 오래 걸릴 수 있는 새 스레드를 시작 (Network, IO)

### RaceCondition 해결방법
[Medium](https://medium.com/swiftcairo/avoiding-race-conditions-in-swift-9ccef0ec0b26)
1. Double Checking
2. Lock
3. Serial Queue
4. Concurrent Queue Barrier

### Struct VS Class

Struct
* call by value (값)
* Stack memory에 할당되기 때문에 속도가 빠름
* 다른 Struct 상속 불가능

Class
* call by reference (참조)
* Heap memory에 할당되기 때문에 속도가 느림
* deinitializer 존재합니다. 
* 다른 Class를 상속 가능

이외에도 많은 차이점이 있습니다.


### OOP -> POP 로 넘어가게된 계기
[링크](http://blog.naver.com/PostView.nhn?blogId=jdub7138&logNo=220968251035&beginTime=0&jumpingVid=&from=search&redirect=Log&widgetTypeCall=true)

Class는 상속이 가능하고 Struct, Enum 은 상속이 불가능하기 때문에 
`데이터 구조`를 보통 Class로 작성되었음

Class 는 참조 타입이기 때문에 멀티 스레딩 환경에서 값이 꼬이는 경우가 많았음.

### Any VS AnyObject VS NSObject
[여기요](https://craiggrummitt.com/2016/09/16/any-vs-anyobject-vs-nsobject-in-swift-3/)
<img src="https://craiggrummitt.files.wordpress.com/2016/09/anyanyobject.png?w=419&h=419&zoom=2" alt="alt text" width="400" >
