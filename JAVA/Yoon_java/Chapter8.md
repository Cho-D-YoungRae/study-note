#### 패키지와 클래스패스
##### 클래스 패스
> 자바 가상머신이 클래스 파일을 찾는 경로

###### 현재 디렉토리를 기준으로 한 실행
* '클래스 패스'를 지정하지 않으면 자바 가상머신은 필요한 클래스를 현재 디렉토리에서 찾는다.

###### 클래스 패스의 지정
* set classpath : 클래스 패스의 확인
* set classpath=<경로> : 클래스 패스 지정
* set classpath=<경로1>;<경로2> : 2개 이상의 경로

##### 패키지의 이해
> 간단하게 설명하면 패키지는 클래스를 묶는 수단이다.

###### 패키지 선언의 의미와 목적
* 클래스를 구분하고 관련 기능을 짐작할 수 있다
* 이름 충돌을 방지할 수 있다

###### 이름 충돌의 해결을 위한 패키지의 효과
**패키지 선언을 통한 두 가지 특성**
* 클래스 접근 방법의 구분
  > 서로 다른 패키지의 두 클래스는 인스턴스 생성시 사용하는 이름이 다르다.
* 클래스의 공간적인 구분
  > 서로 다른 패키지의 두 클래스 파일은 저장되는 위치가 다르다.

**패키지 이름 작성 관례**
* 클래스의 이름과 구분이 되도록 패키지의 이름은 모두 소문자로 구성한다.
* 인터넷 도메인 이름의 역순으로 패키지 이름을 구성한다.
* 패키지 이름의 끝에 클래스를 정의한 주체 또는 팀을 구분하는 이름을 추가한다.


인터넷 도메인이 wxfx.com인 회사의 smart팀에서 개발한 클래스를 묶을 패키지 이름
> com.wxfx.smart

위 패키지의 Circle 인스턴스 생성문장
> com.wxfx.smart.Circle c1 = new com.wxfx.smart.Circle(3.5)

위 패키지의 Circle.class 저장 위치
> \com\wxfx\smart

###### 패키지의 선언 및 컴파일 방법
클래스를 패키지로 묶을 때에는 해당 클래스를 담고 있는 소스파일의 상단에 패키지 선언을 해야한다.
> package com.wxfx.smart

패키지 선언 후 컴파일 한다.
> javac -d <패키지를 생성할 위치 정보> <컴파일할 파일>
>* ex> javac -d . src/circle1/Circle.java
>* 패키지 이름과 동일한 디렉토리 경로가 생성되고 그 안에 클래스 파일 생성된다.
>* 클래스 파일의 디렉토리 이름을 인위적으로 바꾸면 해당 클래스 파일은 찾을 수 없다.
>* 직접 패키지 이름과 동일한 경로의 디렉토리를 만들고 -d 옵션 없이 컴파일 하여 얻은 클래스 파일을 해당 디렉토리에 가져다 놓아도 된다.

###### import 선언
import com.wxfx.smart.Circle;
> Circle c1 = new Circle(3.5);
import com.wxfx.smart.*;
> com.wxfx.smart 패키지로 묶인 클래스 모두 패키지 선언 생략