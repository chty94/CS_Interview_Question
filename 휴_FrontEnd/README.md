## 면접 질문 리스트



### 자료구조

- stack, queue, tree, heap 자료구조에 대해서 설명할 수 있는가? 

### 운영체제

- 세마포어와 뮤텍스의 차이와 어느 상황에서 사용하는가?
- 스레드와 프로세스에 대한 차이점은?
- non-blocking과 blocking의 차이점은?

### Git

- merge와 rebase 차이

### 네트워크

- http와 https의 차이점은?
- SSL과 TLS의 차이점은? 
- tcp는 osi 7계층 중 어느 곳에 속하는가?
- GET method를 사용했을 때 브라우저에 cache저장을 안하려면 어떻게 해야하는지?

### 기타

- MVP 디자인 패턴의 구조는? 또 MVP 디자인 패턴과 유사한 다른 디자인패턴은?
- TDD의 개념과 사용경험이 있는지? TDD외에 다른 개발 방법론에 대해서 아는게 있는지?
- 리팩토링의 개념은?
- oAuth의 개념과 oAuth를 사용하면 좋은점은?
- 프로젝트를 설계했을 때 다이어그램으로 짠 구조 설명
- 프로젝트의 DB 구조 설명
- 어떤 DB를 사용했는지?
- 프로젝트하면서 어려웠던 점이 있었다면?

### 몬티홀 딜레마 문제와 굉장히 유사한 질문

- 3개의 문이 있습니다. 이 중 하나의 문을 열면 다음 단계의 면접으로 진행할 수 있는 길로 이어지지만 나머지 2개의 문은 바로 출구로 이어져서 더 이상 면접을 진행하지 않게 됩니다. 자, 이제 면접관은 지원자에게 2번의 선택 기회를 줍니다. 먼저, 지원자가 3개의 문 중에 하나를 선택합니다. 그리고 면접관은 다른 두 문 중에서 하나를 제외하는데, 그것은 바로 출구로 이어지는 문입니다. 이제 2개의 문이 남아 있는데, 지원자는 2번째 기회로 이전의 선택을 변경하거나 아니면 원래의 선택을 유지할 수 있습니다. 지원자께서는 어떻게 하시겠습니까? 그리고 선택을 변경(유지)한 이유는 무엇입니까? 

  

____



## 자료구조 

 - Stack
   - 선입후출(First In Last Out) 방식으로 데이터에 접근하는 자료구조
 - Queue
   - 선입후출(First In First Out) 방식으로 데이터에 접근하는 자료구조
 - Tree
   - 계층적 관계를 표현하는 자료구조. 트리는 노드로 이루어져 있으며, 각 노드는 0개 이상의 leaf Node를 갖을 수 있다. 
 - Heap
   - 이진완전트리를 배열로 정의하여 사용하는 자료구조 

------



## 운영체제 



### 세마포어와 뮤텍스

### 세마포어

- 개념

  -  프로세스 및 스레드가 공유 자원을 동시에 사용하려는 문제를 해결하기 위한 동기화 도구

- 방식

  - 카운팅 세마포어 
    - 공유 자원 개수만큼 수를 설정하여 critical section에 들어간 프로세스(or 스레드)가 있는 경우 수를 감소하고 critical section에서 벗어나면 다시 수를 증가시키는 방법으로 동기화 문제를 해결하는 방식 
  - 이진 세마포어
    - 오로지 0과 1로만 공유자원을 접근하는 문제를 해결하는 방법. critical section에 들어간 프로세스(or 스레드)가 있는 경우 0으로 수를 변경하여 다른 프로세스가 접근하지 못하도록 만든다. 그리고 공유자원을 사용하고 있던 프로세스가 critical section에서 벗어나면 다시 1로 수를 증가시켜서 다른 프로세스들이 접근이 가능하도록 하여 동기화 문제를 해결하는 방식이다.

- 특징

  - busy waiting을 하지 않는다. 즉 공유 자원을 다른 프로세스가 사용하고 있다면 다른 프로세스들은 block을 시킨다. 이로인해 계속적으로 공유자원을 사용할 수 있는지 확인하는 함수를 수행하지 않아 리소스 낭비를 줄인다.
  - 세마포어는 공유자원의 개수만큼 프로세스(및 스레드)가 접근할 수 있도록 할 수 있으며 이에 대한 동기화 문제를 처리한다.
  - 현재 공유자원을 사용하고 있는 프로세스가 아닌 다른 프로세스가 lock을 해제시킬 수 있다.

  

### 뮤텍스

- 개념
  - 프로세스 및 스레드가 공유 자원을 동시에 사용하려는 문제를 해결하기 위한 동기화 도구
- 특징
  - busy waiting을 발생시킨다. 대기하는 프로세스를 block처리하는 세마포어와 다르게 계속적으로 critical section에 들어갈 수 있는지에 대해서 리소스를 사용한다.
  - 반드시 lock을 갖고 있는 프로세스가 더 이상 공유자원을 사용하지 않을 때 lock 권한을 갖는 프로세스만이 해당 lock을 풀 수 있다.  



------

### Process와 Thread의 차이점

### Process

  - 개념

    - 메모리에서 동작하고 있는 하나의 프로그램을 프로세스라고 한다. 

  - 특징

    - context Switching 시, 리소스 사용량이 멀티 스레딩의 context switching보다 크다. 

    - 외부 메모리를 사용하여 공유자원을 사용해야 한다.

    - 에러로 인해 프로세스가 죽어도 다른 프로세스에 영향을 주지 않는다. 

    - code, data, heap 메모리를 갖고 있다.

    - PCB(Process Control Block)을 갖는다. PCB는 CPU가 프로세스의 일처리를 할 때 참고할 수 있는 모든 정보가 들어가 있는 block이다.
      때문에 Context switching이 발생하면, 현재 작업했던 모든 내용을 PCB에 담고 CPU를 다른 프로세스로 넘긴다. 그리고 다시 CPU를 할당받을 때,
      PCB를 참고하여 다음 번 일 처리를 진행한다. 

    - 동기화 작업이 중요하다.

      

### Thread

  - 개념
    - 프로세스 내부에서 실행되는 하나의 실행 단위를 말한다.
  - 특징
    - context Switching 시, 리소스 사용량이 멀티 프로세싱보다 적다.
    - 별도의 stack 메모리를 갖는다. 모든 스레드가 각자의 stack을 갖는 이유는 멀티 스레딩 시, 각자가 맡은 역할을 처리하기 위해 개별적인 저장공간이
      필요해서이다.
    - 공유 메모리를 프로세스의 heap을 사용하기 때문에 외부 메모리를 참조할 필요가 없다.
    - 에러로 인해 특정 스레드가 중단되면 다른 스레드들도 중단될 수 있다.
    - 동기화 작업이 중요하다. 

------

### non-blocking 과 blocking의 차이점

____



## Git



### Merge와 Rebase

### merge란?
  - 개념
    - 두 커밋을 병합하는 기능을 말한다. 파생된 branch의 root commit과 master branch의 commit이 다르면 새로운 commit을 생성하여 commit을 합친다.
    
      

상황 1. master branch의 commit과 develop 브랜치의 root commit이 동일한 경우 (root 커밋이란 처음 파생된 커밋을 뜻함)

  ![Untitled](https://user-images.githubusercontent.com/45396949/122182171-00122380-cec5-11eb-923e-5997d328d4c7.png)

  develop branch가 가장 최신의 commit인 상황일 때 merge가 된다면 별도로 새로운 커밋을 생성하지 않고 가장 최신의 commit으로 branch를 이동시킨다.

  ![Untitled](https://user-images.githubusercontent.com/45396949/122182534-53847180-cec5-11eb-9cf5-5f4b086480c3.png)

  이처럼 fast-forward가 가장 최신의 커밋을 가르키는 가장 이상적인 상황이기 때문에 그래프가 단순하다.

상황 2. master branch의 commit과 develop 브랜치의 root commit이 달라지는 경우 (root 커밋이란 처음 파생된 커밋을 뜻함)

  ![Untitled](https://user-images.githubusercontent.com/45396949/122183630-63508580-cec6-11eb-8275-13f1a33eb57b.png)

  이처럼 master 브랜치가 가만히 있지않고 계속적으로 생성이 되는 경우에(협업하는 경우에서 주로 발생하는 상황)  merge하면 새로운 커밋을 생성한다.

  ![Untitled](https://user-images.githubusercontent.com/45396949/122183777-8713cb80-cec6-11eb-9715-2d1f8ef0ef14.png)

  새롭게 생성한 커밋에 develop branch와 master 브랜치를 이동시킨다. 단순한 구조여서 이정도지만 여러명이 머지하면 그만큼 commit graph는 복잡해질 것이다. 

### Rebase란?

  - 개념
    - commit을 합칠 때 현재 master branch가 가르키고 있는 commit이 develop branch의 base가 아닐 때 develop의 base를 
    현재 master branch가 가르키고 있는 최신의 branch로 이동시켜서 새로운 commit을 생성하지 않고 commit을 합치는 방법을 말한다.  

  상황 1. master branch의 commit이 계속적으로 만들어져서 브랜치별로 서로 다른 최신 커밋을 갖을 때

  ![Untitled](https://user-images.githubusercontent.com/45396949/122184479-35b80c00-cec7-11eb-9ab1-52dd1ac6c05f.png)

  이처럼 커밋 병합을 하려고 했는데 develop 파생된 root commit은 현재 master branch가 가르키고 있는 commit과 다르다. 따라서 rebase는 master branch가 가르키고 있는 commit으로 develop branch의 root base를 옮기도록 만들고 이를 병합한다. 

  ![캡처](https://user-images.githubusercontent.com/45396949/122184964-b2e38100-cec7-11eb-9be3-3389cc4cecdc.PNG)

  이처럼 base를 최신 branch로 옮긴 후에 합치면 새로운 커밋을 생성하지 않고 commit을 합칠 수 있다. 
____



## 네트워크



### Http 와 Https의 차이점

------

### SSL 과 TLS의 차이점

------

### Get과 Post의 차이점

### Get

- 개념
  - Url에 데이터를 넣어서 서버에게 데이터를 요청하는 방식
- 특징
  - Url에 데이터를 실어야하므로 큰 사이즈의 데이터는 넣지 못한다.
  - get Method는 브라우저에서 cache되어 저장되어 질 수 있다.
  - Url만 봐도 정보를 쉽게 알 수 있다.
  - [브라우저에 cache 안남도록 만들기](https://www.zerocho.com/category/HTTP/post/5b594dd3c06fa2001b89feb9)

### Post

- 개념
  - Body 공간에 요청하고자 하는 데이터들을 넣어서 서버에게 데이터를 요청하거나 수정하는 방식
- 특징
  - Body 안에 데이터를 넣어서 보내기 때문에 더 큰 사이즈의 데이터를 실어서 보낼 수 있다.
  - get method와는 다르게 브라우저에서 캐싱되지 않는다. 
  - Body 공간에 데이터가 있기 때문에 정보가 보이지는 않는다. 하지만 암호화 처리를 안하면 보안 강도는 Get과 비슷하다.
  - 서버에게 데이터를 요청할 뿐 아니라 수정도 요청할 수 있다.

------

### OSI 7계층

------



## 기타



### MVP 디자인 패턴 

 - 구조
   - Model
     - presenter로부터 요구받은 데이터 처리하고 결과를 presenter에게 리턴한다.
   - View
     - 유저로부터 event를 받고 presenter에게 event를 전달한다.그리고 presenter로부터 받은 값으로 UI 갱신한다.
   - Presenter
     - View로부터 받은 이벤트를 처리하는 역할을한다. 

- 특징
  - Presenter는 뷰와 1대1 관계를 갖는다.
  - view와 presenter의 의존성이 강하다. 

 ![캡처](https://user-images.githubusercontent.com/45396949/122187083-a95b1880-cec9-11eb-9fd2-729c4f444898.PNG)



### MVC 디자인 패턴

 - 구조
   - Model
     - Controler로부터 요구받은 데이터를 처리하고 결과를 View에게 리턴한다. 
   - View
     - Controler가 받은 Event에 대한 결과 값 Model로부터 받아서 UI를 갱신하는 한다.
   - Controller
     - 유저로부터 Event를 받고 Model에게 필요한 작업을 수행하도록 제어한다. 

 - 특징
   - Controler는 1대 다 관계를 갖는다.
   - view와 model의 의존성이 강하다. 

------

## TDD (Test-Driven Delvelopment)

- 개념
  - 테스트 코드를 통해서 새로운 기능을 만들어 나가는 방식. 애자일 기법 중 하나로서, 만들고자 하는 기능에 대한 간단한 테스트 코드를 만들고 이를 보안해 나가면서 동작되는 기능을 만드는 개발 방법이다. 즉 테스트 코드를 통과할 때까지 문제없는 코드를 작성해 나간다. 



### 다른 개발  방법론

1. BDD (Behavior-Driven Delvelopment)
   - BDD는 팀원들이 시스템의 예상될 행동을 논의하여 예상되는 기능에 관한 공통된 이해를 구축해 나가는 개발 방식이다. 
2. 스크럼(scrum)
   - 스크럼은 반복적이고 점진적인 개발방법을 말한다. 각 반복주기를 설정하고 주기가 종료될 때마다 부분적으로 완성된 결과물을 만든다. 애자일에서는 반복주기를 이터레이션이라고 하지만 스크럼에서는 스프린트라고 하며 주로 1~4주로 구성한다. 

____
## Refactoring

- 개념
  - 운영중인 서비스를 중단하지 않고 코드를 효율적으로 고쳐나가는 것을 말한다.

____
## oAuth
- 개념

  - 해당 서비스를 이용하기 위해서 권한을 부여받는 것을 말한다. 즉 네이버로 소셜 로그인해서 해당 앱을 이용할 수 있게 만들어준다. 

    

- 탄생 배경

  - 사용자가 여러 어플리케이션에 회원가입하여 자신의 정보가 공유되는 것을 꺼려한다는 문제로부터 시작하여 twitter의 주도로 oAuth 1.0이 만들어졌다.

- 방식

  ![Untitled](https://user-images.githubusercontent.com/45396949/122347182-b983fe00-cf84-11eb-814a-7d47451786d6.png)

1. 클라이언트가 로그인 요청하면 서버는 로그인 페이지 화면을 제공한다.

   

2. 클라이언트가 id 및 pw 제공하면 해당 정보를 검증한 후 권한과 accessToken을 발급해준다. id /pw는 소셜 로그인을 통해서 넘어가고 해당 회사의 인증 서비스에서 검증한다. 내가 만든 서비스가 소셜 로그인을 지원한다면 소셜 로그인으로부터 얻어지는 데이터가 내 서비스에 필수적으로 요구되는 값으로 지정할 수 있어야 한다. 예를들어 accessToken를 매번 API header에 넘겨줘야 이를 실행할 수 있는 것처럼 말이다. 이처럼 제 3의 인증기관에서 넘겨준 데이터를 내 서비스와 연결할 수 있는 구조를 만들어야 한다.

   

3. 사용할 application의 회원가입이 모두 진행됐고 accessToken도 발급받은 상태이므로 이제 이용할 서비스를 요청한다. 3번에서 말한 것처럼 해당 서비스를 이용하기 위해서는 반드시 accessToken을 전송하는 구조로 만든다. 그러면 해당 서비스를 이용할 수 있는 사용자인지 검증 시스템에서 확인한다.

   

4. 서비스 이용이 가능한 사용자라면 해당 서비스를 제공한다.

   

------

