# My Coding Convention
나만의 코딩 컨벤션
## 코딩 컨벤션이 필요한 이유
컨벤션의 뜻: 관습, 대회, 조약, 조약의 의미를 사용하면 조약은 약속의 의미와 비슷하고,  
결국 코딩 컨벤션이라는것은 코딩을 할때의 약속, 즉 코드를 작성하면서 지켜야하는 약속이라고 할 수 있다.  

코드를 작성하면서 서로간의 약속, 즉 규칙을 정해두고 작성하게 되는 이유는, 일반적으로 하나의 단일 프로젝트를 여러명이 개발하게 되는데,  
아무런 규칙 없이 각자의 스타일로 코드를 작성하게 되고, 이는 프로젝트에서 일관된 코드 스타일을 기대하기 힘들게 된다.  
  
로봇이 아닌이상 각자의 코딩스타일은 다를수 밖에 없기 때문에, 다른사람이 작업한부분을 수정하거나 참고해서 읽어야 할때,  
비 일관적인 코드에서 오는 낮선 감정은 가독성을 떨어트리고 우리를 더 피곤하게 할 수 밖에 없다.  
  
그렇기 때문에 코딩 컨벤션을 통해 전체적인 코드의 일관된 스타일을 유지하여 코드의 가독성을 높여서 코드를 더 빠르게 이해할수 있도록 할 수 있기 때문에 사용하는 것이라고 생각한다.  

심지어 혼자서 프로젝트를 진행해도, 당장 몇시간 전에 쓴 코드도 다시 보면 이해가 안될때가 종종 있어서, 더욱이 필수적으로 해야 한다고 생각한다.  
여러곳의 코딩컨벤션을 읽어보고 참조해서 나의 코딩 스타일을 가진 컨벤션을 작성해보고자 한다.  

## 네이밍
### 변수
- 변수 이름은 lowerCamelCase 사용.
- 복수의 의미인 경우 s를 붙이거나, 복수형으로 사용하여 표현하기.

### 함수
- 함수 이름에는 lowerCamelCase 사용.
- 함수명 시작은 동사원형으로
- Event-Handling 함수의 경우 (조동사 + 동사원형)으로 시작하기.
  - will은 특정 행위가 일어나기 직전.
  - did는 특정 행위가 일어난 직후
- 데이터를 가져오는 함수의 경우, get을 사용하지 않고 request, fetch을 대신 사용.
  - request : 에러가 발생하거나, 실패할 수 있는 비동기 작업에 사용. 예를 들어, http 통신을 통해 값을 요청하는 경우.
  - fetch : 요청이 실패하지 않고 결과를 바로 반환할 때 사용. 예를 들어, data를 찾고자 하는 모든 행위를 할 때.

### 열거형
- 열거형의 이름은 UpperCamelCase.
- 열거형의 case에는 lowerCamelCase.

### 구조체와 클래스 
- 구조체와 클래스의 이름은 UpperCamelCase를 사용.
- 구조체와 함수의 이름 앞에 prefix 사용하지 않기.
- 구조체와 클래스의 프로퍼티 및 메소드는 lowerCamelCase를 사용.

### 프로토콜
- 구조를 나타내는 프로토콜은 명사로 작성하기.
- 무언가를 할 수 있음(능력)을 설명하는 프로토콜은 형용사로 작성하기.

### 델리게이트
- 함수의 첫번째 인자는 생략가능한 델리게이트의 소스 객체를 사용.

## 들여쓰기
- 스페이스바 4개를 기본으로 하고, 스페이스바 4번 = 탭 한번
- 함수 호출시 한줄의 문자갯수가 100개가 넘어갈 경우 (,), 파리미터로 구분하여 들여쓰기

## 띄어쓰기
- 콜론(:)사용시 콜론 왼쪽은 공백이 없고, 오른쪽에만 공백 한간 유지하기

## 타입 
- 컴팩트 코드를 선호하고 컴파일러가 단일 인스턴스의 상수나 변수의 타입을 추론하게 하기.
- 필요한 경우 CGFloat나 Int64와 같은 경우는 특정 타입을 지정하기.

## 메모리 관리
- 순환 참조 일어나지 않도록 weak 적절히 잘 사용하기, unowned는 지양하자

## UIKit

### 일반적인 구조 정의

```swift
class CustomView: UIView {

//MARK: - Properties
//MARK: - Components
// MARK: - Initializers
// MARK: - Set
// MARK: - LifeCycle
override func setDefaults(at viewController: UIViewController) {}
override func setHierarchy(at view: UIView) {}
override func setLayout(at view: UIView) {}
// MARK: - Private 
}

// MARK: - DataSource  
extension CustomView: DataSource {
}
// MARK: - Delegate 
extension CustomView: Delegate {
}
```

## Reference

https://github.com/DeveloperAcademy-POSTECH/swift-style-guide?tab=readme-ov-file#%EA%B5%AC%EC%A1%B0%EC%B2%B4%EC%99%80-%ED%81%B4%EB%9E%98%EC%8A%A4
