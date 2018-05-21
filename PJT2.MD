### 2. 회원가입 화면 구현
- [x] 00. Hello!
- [x] 01. Human Interface Guidelines
1. H.I.G(Human Interface Guidelines)
- H.I.G 문서의 가이드라인을 따라 인터페이스를 작성하면 사용자들로 하여금 새로운 애플리케이션을 처음 접하더라도 대부분의 iOS 사용자에게 익숙한 환경을 제공할 수 있다.
  - 상호작용, 일관성, 기준점
  
- [x] 02. 화면의 전환
1. 내비게이션 컨트롤러에 대해 이해합니다.
- 내비게이션 인터페이스
  - 계층적 구조의 화면전환을 위해 사용되는 드릴 다운 인터페이스(각 선택할 수 있는 항목에 대한 세부항목이 존재하는 인터페이스)
- 내비게이셔 컨트롤러
  - 컨테이너 뷰 컨트롤러로써(container view controller) 내비게이션 스택(navigation stack)을 사용하여 다른 뷰 컨트롤러를 관리.
2. 내비게이션 스택에 대해 이해합니다.
- 내비게이션 스택
  - 뷰 컨트롤러를 담을 수 있는 배열
3. 내비게이션 인터페이스를 구현하는 두 가지 방법을 숙지합니다.
- 스토리보드를 사용하여 내비게이션 인터페이스 구성
- 코드작성을 통해 내비게이션 인터페이스 구성
4. 내비게이션바에 관해 간단히 살펴봅니다.
- 내비게이션바는 내비게이션 컨트롤러의 관리를 받는 모든 뷰 컨트롤러의 상단에 표시.
5. 모달(Modal)
- 사용자의 이목을 끌기 위해 사용하는 화면전환 기법(정보의 흐름이 아니라, 이목을 끌기위한 화면)

- [x] 03.뷰의 상태변화 감지
1. 뷰의 상태 변화에 따라 호출되는 메서드와 순서에 대해 이해합니다.
- func viewDidLoad()
  - 뷰 계층이 메모리에 로드된 직후 호출되는 메서드
  - 뷰의 추가적인 초기화 작업을 하기 좋은 시점
  - 메모리에 처음 로딩 될때 1회 호출되는 메서드로, 메모리 경고로 뷰가 사라지지 않는 이상 다시 호출되지 않음
- func viewWillAppear(_ animated: Bool)  
  - 뷰가 뷰 계층에 추가되고 화면이 표시되기 직전에 호출되는 메서드
  - 뷰의 추가적인 초기화 작업을 하기 좋은 시점
  - 다른 뷰로 이동했다가 되돌아오면 재호출되는 메서드로, 화면이 나타날때마다 수행해야하는 작업을 하기 좋은 시점
- func viewDidAppear(_ animated: Bool)  
  - 뷰가 뷰 계층에 추가되어 화면이 표시되면 호출되는 메서드
  - 뷰를 나타내는 것과 관련된 추가적인 작업을 하기 좋은 시점
- func viewWillDisappear(_ animated: Bool) 
  - 뷰가 뷰 계층에서 사라지기 직전에 호출되는 메서드
  - 뷰가 생성된 뒤 발생한 변화를 이전상태로 되돌리기 좋은 시점
- func viewDidDisappear(_ animated: Bool)
  - 뷰가 뷰 계층에서 사라진 후 호출되는 메서드
  - 뷰를 숨기는 것과 관련된 추가적인 작업을 하기 좋은 시점
  - 시간이 오래 걸리는 작업은 하지 않는 것이 좋음
2. 뷰의 레이아웃 변화에 따라 호출되는 메서드에 애해 이해합니다.
- func viewWillLayoutSubviews()
  - 뷰가 서브뷰의 레이아웃을 변경하기 직전에 호출되는 메서드
  - 서브뷰의 레이아웃을 변경하기 전에 수행할 작업을 하기 좋은 시점
- func viewDidLayoutSubviews()
  - 서브뷰의 레이아웃이 변경된 후 호출되는 메서드
  - 서브뷰의 레이아웃을 변경 한 후 추가적인 작업을 수행하기 좋은 시점

- [x] 04. Delegation
1. 델리게이션 디자인 패턴에 대해 알아봅니다.
- Delegation
  - 델리게이션 디자인 패턴은 하나의 객체가 다른 객체를 대신해 동작 또는 조정할 수 있는 기능을 제공
2. 데이터소스와 프로토콜에 대해 알아봅니다.
- 데이터소스(DataSource)
  - 델리게이트가 사용자 인터페이스 제어에 관련된 권한을 위임받고, 데이터소스는 데이터를 제어하는 기능을 위임받음
- 프로토콜(Protocol) 
  - 코코아터치에서 프로토콜을 사용해 델리게이션과 데이터소스를 구현할 수 있습니다.
  - 객체간 소통을 위한 강력한 통신 규약으로 데이터나 메시지를 전달할 때 사용합니다.
  - 프로토콜은 특별한 상황에 대한 역할을 정의하고 제시하지만, 세부기능은 미리 구현해두지 않습니다.
  
- [x] 05. Singleton
1. 싱글턴 패턴에 대해 알아봅니다.
- 싱글턴(SingleTon)
  - 특정 클래스의 인스턴스가 오직 하나임을 보장하는 객체
2. 싱글턴 패턴을 활용하는 Cocoa 프레임워크의 클래스들에 대해 알아봅니다.
- FileManager
  - 애플리케이션 파일 시스템을 관리하는 클래스
  - FileManager.default
- URLSession
  - URL 세션을 관리하는 클래스입니다.
  - URLSession.shared
- NotificationCenter
  - 등록된 알림의 정보를 사용할 수 있게 해주는 클래스
  - NotificationCenter.default
- UserDefaults
  - Key-Value 형태로 간단한 데이터를 저장하고 관리할 수 있는 인터페이스를 제공하는 데이터베이스 클래스
  - UserDefaults.standard
- UIApplication
  - iOS에서 실행되는 중앙제어 애플리케이션 객체
  - UIApplication.shared
  
- [x] 06. Target-Action
1. Target-Action 디자인 패턴이 무엇인지 이해합니다.
- Target-Action 디자인 패턴
  - 객체는 이벤트가 발생할 때 다른 객체에 메시지를 보내는 데 필요한 정보를 포함
2. Target-Action 디자인 패턴에서 액션 메서드의 형식에 대해 숙지합니다.
```
// 프로그래밍 방식
@objc func doSomething(_ sender: Any) {

}

// 인터페이스 빌더
@IBAction func doSomething(_ sender: Any) { 

}
```
3. 컨트롤 이벤트와 액션 메서드의 관계에 대해 살펴봅니다.
- 컨트롤 객체에서 특정 이벤트가 발생하면, 미리 지정해 둔 타겟의 액션을 호출

- [x] 07. Gesture Recognizer
1. 제스처 인식기에 대해 알아봅니다.
- Gesture Recognizer
 - 여러 제스처 관련 이벤트를 인식
 - 특정 제스처 이벤트가 일어날 때 마다 각 타깃에 맞는 액션 메시지를 보내어 제스처 관련 이벤트를 처리
2. UIGestureRecognizer의 하위클래스를 통해 어떤 제스처를 인식할 수 있는지 알아봅니다.
- UITapGestureRecognizer : 싱글탭 또는 멀티탭 제스처
- UIPinchGestureRecognizer : 핀치(Pinch) 제스처
- UIRotationGestureRecognizer : 회전 제스처
- UISwipeGestureRecognizer : 스와이프(swipe) 제스처
- UIPanGestureRecognizer : 드래그(drag) 제스처
- UIScreenEdgePanGestureRecognizer : 화면 가장자리 드래그 제스처
- UILongPressGestureRecognizer : 롱프레스(long-press) 제스처

- [x] 08. Summary
