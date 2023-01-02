# Kokoa Clone 2022 Update

=========================

### 목적 : HTML & CSS로 반응형 Web을 만들어 보자.

### 제작 하면서 알게되는 내용을 메모 및 정리 한다.

### Note

- Visual Studio Code(VSCode)에서 멀티커서 사용하기
  Multiple selections(multi-cursor)
  사용법 내용
  Alt + Click 클릭한 부분에 커서를 추가함
  Ctrl + Alt + ↓(↑) 현재 커서 기준 위, 아래에 커서를 추가함(방향키 이용)
  Ctrl + D 현재 커서가 위치한 단어를 선택하고, 일치하는 다음 단어도 하나하나씩 선택함
  Ctrl + Shift + L Ctrl + D 방식은 하나하나 선택하는 방식이라면, 이 방식은 한 번에 모든 것을 선택해줌
  Shift + Alt + 드래그 Column (box) selection, 현재 커서 기준 드래그한 곳까지 다중 선택
  마우스 휠 클릭 + 드래그 Column (box) selection, 휠 클릭한 부분부터 드래그한 곳까지 다중 선택
  ESC 멀티 커서 취소

- BEM (Block Element Modifier)
  변수, 함수, 클래스 등의 '이름 짓기'시 어떤 이름이 깔끔하고, 겹치지 않으며 재사용할 수 있고, 다른 사람이 한번에 팍하고 알아볼 수 있을까?
  BEM은 Block, Element, Modifier의 줄임말로 CSS 방법론 중 하나로, 스타일링 구조를 정의한다.
  기본 구조는 [block__element--modifier]이다.
  관련 규칙 (https://en.bem.info/methodology/quick-start/)

- 아이콘의 제작 방법
  (1) 직접 이미지를 만들고 추출하는 방법
  (2) svg 파일(픽셀이 없는 이미지 파일 형식으로 수학으로만 구성된 형식. 좌표로만 이루어져 원하는 만큼 늘릴 수 있음)을 사용.
  https://heroicons.com/, https://fontawesome.com/icons

- Font
  구글 폰트 활용 (https://fonts.google.com/)
  폰트 다운로드 가능, 경로 링크 제공 및 폰트 그룹 지정 제공.

- CSS 적용
  CSS 폴더 생성
  Components, Screens 별 폴더 생성
  /css reset.css 생성 및 Reset구문 저장.(브라우저 기본값 제거용)
  /css style.css 생성 각 화면, 또는 컴포넌트 별 CSS import
  HTML 파일에 style.css link 연결 <head> 맨위에 link:css 입력하면 링크 자동 생성
  컴포넌트나 각 화면별 스타일은 각각 CSS 파일 작성하여 해당 폴더에 저장. style.css 파일에 import하여 사용.
  css 파일 import 순서 중요함. 1. 폰트 2. 리셋 3. 바리에이블(공통적용) 4. 각 폴더별

- HTML <form>에서는 action, method 사용이 가능하다.
  action에 html 파일명을 넣어 해당 페이지로 이동이 되도록 action을 지정이 가능하다.
  method는 post 방식과 get 방식이 있음. post방식은 보안이 되고, get은 보안에 취약하다.(url에 입력 내용이 보임.)
  단축키
  link:css style.css 링크 자동생성
  [nav>ul>li*4>a]
    <nav>
      <ul>
        <li><a href=""></a></li>
        <li><a href=""></a></li>
        <li><a href=""></a></li>
        <li><a href=""></a></li>
      </ul>
    </nav>
    상속관계의 코드를 한번에 작성. 
  [.user-component__column*2]
    <div class="user-component">
      <div class="user-component__column"></div>
      <div class="user-component__column"></div>
    </div>
    <div> 사이에 클래스 입력하면 자동작성 </div>
    
- CSS
  box-sizing: border-box; padding 값과 상관없이 박스 사이즈 유지하도록 하는 옵션.
  본래 CSS에서는 padding을 지정하면 패딩크기 만큼 박스사이즈를 늘린다. (패딩은 컨텐츠가 들어갈수 없는 공간.)
  position : absolute를 사용하기 위해서는 부모에 relative를 선언해 주어야한다.
  justify-items/content : 가로정렬
  align-items/content : 세로정렬
    items : flex line을 기준으로 아이템을 정렬
    contents : flex line을 정렬
    flex-end : 뒤집기 (justify-items/content-가로, align-items/content-세로)
  .class1, .class2 {} : class1 class2 모두 적용
  .class1 .class2 {} : class1에 종속된 class2에만 적용
  animation: hideSplashScreen 0.4s ease-in-out forwards; forward 애니메이션의 마지막 값을 유지
  animation-delay: 1s; 애니메이션시작지연
  visibility: hidden; 화면 감춤 (아래 레이어 사용가능하게됨)
  will-change: transform; 엘리먼트에 무엇이 바뀔 것인지 미리 알려주는 함수(예시는 transform). 그래픽카드로 애니메이션 가속

- Git hub 웹 퍼블리싱
  프론트 앤드만 지원, 퍼블릭 저장소이어야만 한다.
  Branch를 무조건 "gh-pages"로 만든다.
  퍼블리쉬 브런치 버튼 누른다.
  URL=id.github.io/저장소명
