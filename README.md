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

### MVC MVP MVVM
[마기님 블로그](https://magi82.github.io/android-mvc-mvp-mvvm/)
#### MVC 
1. Controller로 사용자의 입력이 들어옵니다.
2. Controller는 Model을 데이터 업데이트 및 불러오고
3. Model은 해당 데이터를 보여줄 View를 선택해서 화면에 보여주게 됩니다.

MVC는 단점이 있습니다. View와 Model이 서로 의존적이라는 점입니다.

<img src="https://magi82.github.io/images/2017-2-24-android-mvc-mvp-mvvm/mvc.png" alt="alt text" width="400" height="whatever">

#### MVP
1. View로 사용자의 입력이 들어옵니다.
2. View는 Presenter에 작업 요청을 합니다.
3. Presenter에서 필요한 데이터를 Model에 요청 합니다.
4. Model은 Presenter에 필요한 데이터를 응답 합니다.
5. Presenter는 View에 데이터를 응답 합니다.
6. View는 Presenter로부터 받은 데이터로 화면에 보여주게 됩니다.

이런 MVP도 단점이 있습니다. View와 Model은 의존성이 없는 대신
View와 Presenter가 1:1로 강한 의존성을 가지게 됩니다.

<img src="https://magi82.github.io/images/2017-2-24-android-mvc-mvp-mvvm/mvp.png" alt="alt text" width="400" height="whatever">

#### MVVM
1. View에 입력이 들어오면 Command 패턴으로 ViewModel에 명령을 합니다.
2. ViewModel은 필요한 데이터를 Model에 요청 합니다.
3. Model은 ViewModel에 필요한 데이터를 응답 합니다.
4. ViewModel은 응답 받은 데이터를 가공해서 저장 합니다.
5. View는 ViewModel과의 Data Binding으로 인해 자동으로 갱신 됩니다.

<img src="https://magi82.github.io/images/2017-2-24-android-mvc-mvp-mvvm/mvvm.png" alt="alt text" width="400" height="whatever">

### Process VS Thread
#### Process
프로세스는 실행 중인 프로그램으로 디스크로부터 메모리에 적재되어 CPU 의 할당을 받을 수 있는 것을 말한다. 운영체제로부터 주소 공간, 파일, 메모리 등을 할당받으며 이것들을 총칭하여 프로세스라고 한다.

#### Thread 
한 프로세스 내에서 동작되는 여러 실행 흐름으로 프로세스 내의 주소 공간이나 자원을 공유할 수 있다.

### ResponderChain
[이동건님 블로그](https://baked-corn.tistory.com/129)
UIResponder 클래스의 객체로 서브클래스로는 UIView, UIViewController, UIApplication 등이 있습니다.
이벤트가 발생하게 되면 앱은 해당 이벤트를 처리할 수 있는 가장 적절한 응답자 객체에게 이벤트 데이터를 전달하고 이를 *first responder*라 합니다.
<img src="https://docs-assets.developer.apple.com/published/7c21d852b9/f17df5bc-d80b-4e17-81cf-4277b1e0f6e4.png" alt="alt text" width="600" height="whatever">
만일 UITextField에 이벤트가 들어왔다고 가정했을 때 UITextField가 해당 이벤트를 처리하지 않는다면 그 이벤트 객체는 부모 뷰인 UIView에게 넘어가고 역시 처리되지 않으면 UIViewController , UIWindow 순으로 거슬러 올라가며 자신을 처리해줄 응답자 객체를 찾습니다. 하지만 끝까지 처리되지 않은 이벤트들은 버려지게 됩니다.

### HitTest 
[Zedd님 블로그](https://zeddios.tistory.com/536)
Hit Testing은 간단히 설명하자면 터치 이벤트가 발생한 뷰를 찾는 행위입니다. 조금 더 설명을 덧붙이자면 터치 이벤트가 발생한 최상단 뷰를 찾는 행위입니다. 그리고 그렇게 찾은 뷰가 해당 이벤트를 처리할 수 있는 첫 번째 뷰, 즉 First Responder가 되는 것입니다.
<img src="http://d33wubrfki0l68.cloudfront.net/60d215400d2340e2334016ea6914aef24cfe6939/d4938/images/hit-test-depth-first-traversal.png" alt="alt text" width="600" height="whatever">
1. 가장 먼저 뷰 계층에 있어서 최상위인 UIWindow가 hitTest(_:with:) 메소드를 호출합니다. 그리고 내부적으로 point(inside:with:) 메소드로 현재 터치 이벤트가 발생한 지점이 UIWindow의 내부인지를 판단합니다. 내부이기 때문에 true 를 반환하고 그의 subviews인 MainView의 검사를 시작합니다.
2. MainView 역시 hitTest(_:with:) 메소드를 호출하여 1번과 같은 과정을 진행합니다. 역시 true가 반환되므로 MainView의 subviews들을 순회하며 검사하게 되는데 Sibling 관계의 깊이 순서에 의해 viewC를 가장 먼저 검사합니다.
3. 하지만 터치한 위치를 보면 해당 지점은 viewC에 속하지 않습니다. 그렇기 때문에 point(inside:with:) 메소드는 false를 반환하고 hitTest(_:with:) 메소드는 nil을 반환합니다. 그로인해 viewC의 subviews들의 검사는 생략됩니다. 그리고 그 Sibling 관계에서 다음 순서인 viewB를 검사하게 됩니다.
4. viewB는 hitTest(_:with:)와 point(inside:with:) 검사를 통과하기 때문에 subviews의 검사가 진행됩니다. 그리고 Sibling 관계의 깊이 순서에 의해 viewB.2를 먼저 검사하게 됩니다.
5. 하지만 3번의 과정과 마찬가지로 viewB.2는 터치 지점을 포함하지 않기 때문에 지나치게 되고 viewB.1 뷰의 검사가 진행됩니다.
6. 마침내 viewB.1의 검사가 진행되고 위와 같은 과정으로 viewB.1이 터치 이벤트가 발생한 최상단 뷰로 판정됩니다.

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
