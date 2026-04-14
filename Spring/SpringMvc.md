# Spring MVC
#### Model-View-Controller의 약자로, 애플리케이션의 세 가지 핵심 책임 영역을 분리하여 각 부분을 독립적으로 개발하고 변경할 수 있도록 하는 소프트웨어 패턴이다.
<br>
<br>


- <b>Model</b> -> 애플리케이션의 데이터와 비즈니스 로직을 관리함. (데이터베이스 등) 
    - 뷰나 컨트롤러에 종속되지 않고 독립적이다.

    <br>
- <b>View</b> -> 사용자에게 보여지는 화면(UI)이다. 모델로부터 데이터를 받아와 사용자에게 시각적으로 표현함.
<br>
<br>

- <b> Controller</b> -> 사용자의 요청을 받아 처리하고 모델과 뷰를 연결한다. 요청을 해석하고, 적절한 모델을 호출하여 데이터를 처리한 후, 그 결과를 보여줄 뷰를 선택하여 전달하는 최종 부분.

<br>
<br>
<hr>
이러한 분리를 통해 각 영역의 변경이 다른 영역에 미치는 <mark>영향을 최소화</mark>하고, <mark>재사용성과 테스트 용이성</mark>을 높일 수 있다!

<br>
<br>
<br>
<br>

# 핵심 구성 개념
<br>
<br>

- <b>DispatcherServlet</b> : Spring MVC의 가장 핵심적인 Front Controller이다. 클라이언트로부터 모든 요청을 가장 먼저 받아 처리 후 다른 하위 컴포넌트들에게 위임하고, 받은 최종 결과를 사용자에게 전달한다.
<br>
<br>

- <b>HandlerMapping</b> : 클라이언트의 요청 URL을 분석하여 요청을 처리할 Controller를 찾아주는 역할이다. (ex : @RequestMapping)
<br>
<br>

- <b> Controller </b> : 클라이언트의 요청을 실제로 처리하는 비즈니스 로직이다. 요청 파라미터를 읽고, 필요한 경우 서비스 계층을 호출하여 데이터를 처리한 후, 처리 결과를 Model에 담아 View 이름과 함께 반환한다. 
<br> (ex : @Controller) 
<br>
<br>

- <b> ModelAndView </b>: 컨트롤러가 처리한 데이터와 뷰의 이름을 함께 담아 DispatcherServlet에 반환하는 객체이다.
<br>
<br>

- <b> ViewResolver </b>: 컨트롤러가 반환한 View의 이름을 실질적인 뷰 리소스로 매핑해준다.
<br>
<br>

- <b> View </b>: ViewResolver가 찾아준 실제 뷰 템플릿이다. Model로부터 전달받은 데이터를 이용하여 HTML과 같은 웹 페이지를 최종적으로 생성하여 DispatcherServlet에 전달한다.
<br>
<br>
<br>
<br>

# Spring MVC 단계


<br>

1. <b>클라이언트 요청 (HTTP Request)</b><br>
<span style="color: gray;">클라이언트의 요청을 받은 후 하위 컴포넌트에게 위임</span>

<br>

2. <b>DispatcherServlet</b>  
<span style="color: gray;">모든 요청을 가장 먼저 받는 Front Controller</span>

<br>

3. <b>HandlerMapping</b> 
<span style="color: gray;">요청 URL을 분석해서 어떤 Controller로 보낼지 결정 </span>

<br>

4. <b>Controller</b>  
 <span style="color: gray;">파라미터 처리, 서비스 호출, 결과 데이터 저장, view 이름으로 반환 </span>


<br>

5. <b>ModelAndView</b>  <mark>!객체!</mark>
<span style="color: gray;">Controller의 결과인 model과 view 이름을 담아 반환 </span>

<br>

6. <b>ViewResolver</b>  
<span style="color: gray;">View 이름을 실제 파일로 변환</span>

<br>

7. <b>View</b>  
<span style="color: gray;">Model 데이터를 이용해서 HTML 생성하는 등 최종 화면 제작</span>

<br>

8. <b>클라이언트 응답 (HTTP Response)</b>  
<span style="color: gray;">완성된 화면을 사용자에게 전달 후 종료</span>

<br>
<br>
<br>
<br>

# Spring MVC의 장단점

<br>

> ## 장점

 <b>

- Model / View / Controller 등 역할이 나뉘어져 있다.</b>  
코드 이해, 유지보수 쉬움

<br>

- <b>구조가 분리되어 있어서 다른 기술로 쉽게 교체 가능하다.</b>  
유연성, 확장성이 용이


<br>

- <b>안정성이 높다</b>  
각 부분을 따로 테스트 가능하다.



> ## 단점

- <b>코드가 복잡하고 디버깅이 어렵다.</b>  
단, 이점은 위의 장점이 되어줄 수도 있다.

<br>

 - <b> 설정이 번거롭다. </b> <br>
 단순한 기능을 구현함에도 여러 클래스가 필요
<br>
<br>
<br>
<br>


# 요약

 요청<small>Model</small> 하고 <br> 
 <small>처리View</small> 하고 <br>
   응답<small>Controller</small> 을 화면에 전달하는 핵심 기능 <br>


