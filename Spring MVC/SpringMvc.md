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

# 핵심 구성 요소
<br>
<br>

- <b>DispatcherServlet</b> : Spring MVC의 가장 핵심적인 Front Controller이다. 클라이언트로부터 모든 요청을 가장 먼저 받아 처리 후 다른 하위 컴포넌트들에게 위임하고, 받은 최종 결과를 사용자에게 전달한다.
<br>
<br>

- <b>HandlerMapping</b> : 클라이언트의 요청 URL을 분석하여 해당 요청을 처리할 Controller(핸들러)를 찾아주는 역할을 합니다. (예: @RequestMapping 어노테이션 기반) 🗺️
<br>
<br>

- <b> Controller </b> : 클라이언트의 요청을 실제로 처리하는 비즈니스 로직을 포함합니다. 요청 파라미터를 읽고, 필요한 경우 서비스(Service) 계층을 호출하여 데이터를 처리한 후, 처리 결과를 Model에 담아 View 이름과 함께 반환합니다. (예: @Controller 어노테이션) 💻
<br>
<br>

- <b> ModelAndView </b>: 컨트롤러가 처리한 데이터(Model)와 뷰의 논리적인 이름(View Name)을 함께 담아 DispatcherServlet에 반환하는 객체입니다. 📦
<br>
<br>

- <b> ViewResolver </b>: 컨트롤러가 반환한 View의 논리적인 이름(예: "home")을 실제 물리적인 뷰 리소스(예: "/WEB-INF/views/home.jsp")로 매핑해주는 역할을 합니다. 🧩
<br>
<br>

- <b> View </b>: ViewResolver가 찾아준 실제 뷰 템플릿(예: JSP 파일)입니다. Model로부터 전달받은 데이터를 이용하여 HTML과 같은 웹 페이지를 최종적으로 렌더링(생성)하여 DispatcherServlet에 전달합니다. 🖼️