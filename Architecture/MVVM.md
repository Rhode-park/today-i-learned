# MVVM

## 개요
`View` - `ViewModel` - `Model`의 세 계층으로 구분한 아키텍처

<br/>

## 개념
`View` - `ViewModel` - `Model`의 세 계층으로 구분한 아키텍처를 말한다.
`View`는 `ViewModel`을 알고 있지만, `ViewModel`은 `View`를 알지 못한다.
`ViewModel`은 `Model`을 알고 있지만, `Model`은 `ViewModel`을 알지 못한다.
즉, `View`가 `ViewModel`을, `ViewModel`이 `Model`을 소유하는 구조이다.

<br/>

### 개념별 설명
| 개념 | 설명 | 
| -------- | -------- | 
| Model     | 애플리케이션에서 데이터를 저장하고 처리하는 계층 | 
| ViewModel     | 애플리케이션에서 `View`와 `Model`사이에 존재하며 서로를 중재하는 역할을 수행하는 계층 <br/> ▪️`View` - `ViewModel`: 사용자와 뷰의 상호작용(클릭, 키보드 동작 등)을 수신한 후, 이에 대한 처리를 데이터 바인딩을 통해 `View`와 `ViewModel`을 연결한다 <br/> ▪️`Model` - `ViewModel`: 데이터를 가져오거나 갱신한 후, `ViewModel`에서 이에 대한 로직을 처리한다 |
| View     | 애플리케이션에서 사용자가 직접 보는 화면(UI)을 담당하는 계층 |
| Data Binding     | `View`와 `ViewModel`을 연결하는 프로세스 <br/> `Model`과 UI요소 간의 싱크를 맞춰주는 것 <br/> 데이터 바인딩 방법: <br/> ▪️ KVO <br/> ▪️ Delegation <br/> ▪️ Functional Reactive Programming <br/> ▪️ Property Observer |
| Business Logic     | 도메인에 맞게 데이터를 변환하고 가져오는 과정 <br/> `View`에 넘겨줄 데이터가 만들어지고 가공되는 과정 |

<br/>

### MVVM 아키텍처의 흐름

![image](https://github.com/Rhode-park/today-i-learned/assets/116149325/4bb65ba0-dfa3-4696-b809-00e6c25ced4a)

1. `View`에 입력이 들어오면 `ViewModel`에게 명령을 함
2. `ViewModel`은 필요한 데이터를 `Model`에게 요청함
3. `Model`은 `ViewModel`에게 요청된 데이터를 응답함
4. `ViewModel`은 응답 받은 데이터를 가공해서 저장함
5. `View`는 `ViewModel`과의 Data Binding으로 인해 자동으로 갱신됨

<br/>

## MVVM의 도입 배경

<br/>

## MVVM의 장단점

| 장점 | 단점 |
| -------- | -------- |
|▪️`View`와 `Model`이 서로를 전혀 알지 못하기 때문에 독립성을 유지할 수 있음 <br/> ▪️ `View`와 `ViewModel`을 바인딩하기 때문에 코드의 양이 줄어듦 <br/> ▪️ `ViewModel`에 UI 관련 코드가 없고 `Controller`와의 의존성이 없기 때문에 UnitTest를 하기에 좋음 | ▪️간단한 UI에서 오히려 `ViewModel`을 설계하는 어려움이 있음 <br/>▪️ Data Binding이 필수적으로 요구됨 <br/>▪️표준화된 틀이 존재하지 않아 사람마다 이해가 다름 |

![image](https://github.com/Rhode-park/today-i-learned/assets/116149325/ba74690e-eef6-49e0-9b7e-38cee903864c)


<br/>

## MVVM 적용시 Rhode만의 규칙

<br/>

## 참고 자료

[평범한 개발자의 개발 여정 - MVVM 패턴](https://jhtop0419.tistory.com/21)

[A Complete Guide And Comparison Of MVC and MVVM
](https://www.intuz.com/blog/guide-on-mvc-vs-mvvm)
