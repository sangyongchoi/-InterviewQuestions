# -InterviewQuestions

**Spring MVC의 동작방식**

1. Servlet가 받은 요청을 HandlerMapping으로 넘어간다.

2. HandlerMapping이 알맞은 Controller를 찾아간다.

3. ViewResolver는 Controller에게 받은 View에 Model에 담겨있는 data를 이용하여 알맞은 페이지를 표현해준다.



**DI란 무엇이고 왜 사용하는가** 

객체간의 의존성을 외부에서 주입시켜 주는것이다. 의존성을 외부에서 주입받으면 모듈간의 결합도가 낮아져서 유연한 변경이 가능하게된다.



**Bean의 생성과 사용이 어떠한 방식으로 이루어집니까?**

Bean은 IoC 컨테이너에 등록된 객체를 뜻한다.

실행시 ComponentScan에 의해 설정파일들을 읽어 BeanFactory에 등록하게 됩니다.

사용시 getBean을 통하여 컨테이너에 등록되어 있는 객체를 가져오게됩니다.



**Bean사용시 발생할 수 있는 문제점**

Bean은 디폴트값으로 싱글톤패턴으로 관리된다.

그렇기 때문에 싱글톤패턴의 문제점인 멀티스레드 환경에서 스레드세이프하지 않다는 단점이 있다.

holder에 의한초기화 (다른분의 블로그를 보고 찾은 해결방법이기 때문에 세세하게 다루지는 않겠습니다. 싱글톤 스레드세이프라고 검색하시면 나올겁니다.)



**빌더패턴이란 무엇입니까?**

복합 객체의 생성 과정과 표현 방법을 분리하여 동일한 생성 절차에서 서로 다른 표현 결과를 만들 수 있게 하는 패턴이다. 파라미터가 많을경우 사용하면 가독성이 좋아진다는 장점이있다.

뿐만아니라 인자의 순서가 상관없어지며 불필요한 생성자를 만들지않는다.

단점으로는 lombok을 사용하지않을경우 별도의 코드를 작성해주어야한다.



**싱글톤패턴이란?**

최초 한번만 메모리를 할당하고 그 메모리에 인스턴스를 생성하여 사용하는 것

싱글톤으로 만들어서 사용하게된다면 다른클래스의 인스턴스들이 데이터를 공유하기 쉽다.

문제점으로는 다중스레드환경에서 인스턴스가 여러개 생성되는 문제점이 발생될 수 있어서 주의해서 사용해야한다.



**Spirng Boot란 무엇입니까 ?**

제품수준의 Spring기반 Application을 만들수 있도록 도와준다. 
개발자가 일일히 정의하지않아도 가장 널리 사용된다고 생각되는 설정을(Spring뿐만 아니라 제 3의 라이브러리까지) 
기본적으로 제공해준다. 
Spring개발을 할때 더 빠르고 폭넓은 사용성을 제공해주는것과 
일일히 설정하지 않아도 설정되어져있는것들을 기본으로 제공해준다. 그러나 개발자가 쉽고 빠르게 원하는대로 바꿀 수 있다. 
security같은 다양한 기능을 제공해주며 더이상 xml설정과 code generation을 하지않는다.



**JPA란 무엇입니까?**

JAVA 기반의 ORM 표준이며 애플리케이션과 JDBC API사이에서 동작하여 데이터베이스에 접근합니다.

JPA에게 객체를 넘기면 Entity분석, 쿼리생성, JDBC API를 이용하여 DB에 접근합니다.

SQL중심 개발에서 객체중심 개발이 가능하고 생산성이 뛰어납니다.

테이블의 생성 변경 관리가 간편하여 유지보수면에서 이점이 있습니다.

패러다임 불일치를 해결했습니다.



**RDBMS란 무엇입니까?**

DB의 레코드들을 삽입 삭제 수정 탐색 할 수 있도록 해주는 소프트웨어로 가장 대중적으로 사용되는 DBMS입니다.

모든 데이터를 2차원 테이블 형태로 표현하는 관계형 데이터 모델에 기초를 두었습니다.

E-R모델을 사용하여 모델링을 하며 테이블의 중복정보는 최소화 시킵니다.

테이블-컬럼형태의 데이터 저장방식을 사용하며 각 열은 특정 종류의 데이터를 수록하며 필드는 속성의 실제 값을 나타냅니다.

테이블의 각행은 한 객체 또는 엔티티와 관련된 값들의 모음을 나타내며 기본키로 표시할 수 있고 여러 테이블에 있는행들은 외래키를 사용하여 상호 연결될 수 있습니다.

테이블과 테이블간의 연관관계를 이용하여 필요한 정보를 구하는 방식을 사용합니다.

보안,권한, 트랜잭션 관리와 같은 기능을 지원합니다.



**Rest API란 무엇입니까 ?**
자원기반의 구조설계의 중심에 리소스가 있고 HTTP Method를 통해 리소스를 처리하도록 설계된 아키텍쳐입니다.
특징으로는 서버에 있는 모든 리소스는 각 리소그당 클라이언트가 바로 접는할 수 있는 URI가 존재하고 경로는 동사보다는 명사 언더바보다는 하이픈 대문자보다는 소문자 파일확장자는 제거하는것이 일반적입니다. 
모든 요청은 클라이언트가 요청할때마다 필요한 정보를 주기때문에 서버에서는 세션정보를 보관할 필요가 없습니다. 
그렇기 때문에 자유도가 높아지고 유연한 아키텍쳐 적용이 가능합니다. 
뿐만 아니라 HTTP메소드를 사용하는데 그중 GET POST PUT DELETE가 일반적으로 많이 사용됩니다. 

장점으로는 언어와 플랫폼에 독립적이며 개살이 쉽고 단순합니다. HTTP를 이용하기때문에 기존 웹인프라를 사용할 수 있습니다. 
반면에 HTTP프로토콜만 이용이 가능하며 p2p통신 모델을 가정했기 때문에 둘 이상을 대상으로 하는 분산환경에는 유용하지가 않습니다. 
또한 보안,정책등에 대한 표준이 없기때문에 관리가 어렵다는 단점이 있습니다. 



**객체지향의 5대원칙은 무엇입니까?**

1. 단일책임원칙으로 작성된 클래스는 하나의 기능만 가지며 제공하는 모든 서비스는 하나의 기능을 수행하는데 집중되어야한다.

2. 기존의 코드를 변경하지않고 기능을 수정하거나 추가할 수 있어야한다.

3. 자식은 부모의 기능을 수행할 수 있어야한다.

4. 의존관계를 맺을때 변화가 거의 없는것에 의존해야한다.

5. 자신이 사용하지않는 인터페이스는 구현하지 않아야한다.



**객체지향 언어의 장점**

1. 코드의 재사용률이 높아진다.

2. 코드의 관리가 용이하다.

3. 신뢰성이 높은 프로그램을 작성할 수 있다.



**TDD란 무엇인가?**

개발하는과정에서 우선 테스트를 작성하고 그걸 통과하는 코드를 만들고 반복하면서 제대로 동작하는지에 대해 피드백을 받는 테스트 주도개발이다.

각각의 코드의 기능에 맞는 케이스가 존재하므로, 코드가 수정되거나 리팩토링할때 버그 또는 오류의 가능성을 낮춰주므로 코드를 안정적으로 개발할 수 있지만 테이스 케이스개발에 소요되는 시간으로 개발시간이 늘어난다는 단점이 있다.



