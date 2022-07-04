## 1차 프로젝트 Front-end/Back-end 소개

- 국내 향수 커머스 사이트 [PAFFEM](https://paffem.me/) 클론 프로젝트 입니다.
- 짧은 프로젝트 기간동안 개발에 집중하기 위해 디자인/기획 부분만 클론했습니다.
- 개발은 초기 세팅부터 모두 직접 구현했으며, 프로젝트에서 구현한 기능은 모두 백엔드와 연결하여 실제 사용할 수 있는 서비스 수준으로 개발했습니다.

### 개발 인원 및 기간

- 개발기간 : 2022/6/20 ~ 2022/7/1
- 개발 인원 : 프론트엔드 4명, 백엔드 2명
- [백엔드 github 링크](https://github.com/wecode-bootcamp-korea/34-1st-Nose-backend/pulls)
- [프론트 github 링크](https://github.com/wecode-bootcamp-korea/34-1st-Nose-frontend/pulls)

### 프로젝트 선정이유

- 이 사이트는 국내 퍼스널 향수를 가이드 해주는 사이트로, perfume teller 라는 서베이 서비스를 통해 향수가 처음인 사람들도 설문을 통해 향수를 추천해 주는 기능이 있어 선정했습니다.
- 백엔드와 프론트엔드의 기능 구현이 적절하게 나눠있어 1차 프로젝트로 적절하다고 판단해 선정했습니다.

<br>

## 적용 기술 및 구현 기능


### 적용 기술

React.js, sass



#### Main
- [슬라이드,캐러셀 이미지 구현] 좌,우 버튼 눌렀을 때, 여러장의 이미지가 한장씩 보이도록 구현했습니다. width : 100%, 100vw로 반응형 웹페이지가 되도록 했습니다.
- [링크관리] 제품교환 서비스, Shop, perfumeTeller,자세히보기, 상품리뷰 등 클릭시 페이지 이동을 구현했습니다.

#### Survey
-[중첩라우팅 구현] Router.js 에서 Survey 컴포넌트에 Survey/* 를 부여하여 Survey/ 뒤에 붙는 url값은 모두 중첩 라우팅을 구현한 Survey.js 파일에서 참조하도록 하였습니다.
- SurveyName.js 에서 유저로부터 받은 name을 SuveyResult.js 에서 보이도록 구현했습니다. QueryString을 통해 데이터를 넘겨주었습니다.
- SuveyName 뿐만 아니라, 다른 페이지에서도 설문을 통해 받은 데이터값을 QueryString으로 SuveyResult 까지 전달하도록 구현했습니다. 

#### Nav/Footer
- [Nav - 스크롤 이벤트 구현] window에 EventListener를 부여하여 scrollY, scrollTop 값을 받도록 하고, 그 값이 >5 일때 색이 반전되도록 구현했습니다.
- [Nav - Modal 구현] openModal(boolean) state로 mouseOver 했을 때, 모달이 열리도록 구현했습니다.
- [Nav,Footer - Link 구현] 클릭시 페이지 이동 구현
#### Login
- 로그인 아이디 패스워드 입력시 onChange함수로 구현하여 로그인 버튼 활성화 기능.
- 로그인 활성화 될 시 메인페이지. 로 네비게이트 구현.
- fetch 함수 사용하여 백엔드서버 통신을 통해 account값과 password 두 값의 -조건에 맞춰 들어간 후 통신 완료.

#### Signup

[회원가입 input values]
- 필수 데이터인 아이디, 패스워드, 휴대폰번호, 이메일 value 값을 비구조할당 및 스프레드 오퍼레이터를 사용해서 객체에 저장
- 정규표현식 조건을 걸고 삼항연산자 및 스프레드 오퍼레이터를 사용해 조건에 부합하지 않으면 경고 message의 빨간색이 active 되게 설정

[회원가입 버튼 활성화]
- 삼항연산자로 걸어둔 조건이 모두 true라는 조건을 변수에 담고 버튼에 disabled 기능으로 true면 disabled를 false를 하고 반대면 활성화
- 백엔드와의 통신으로 데이터 유효성 검사. 정규표현식에 걸어둔 조건에 부합할 시, 통신에 성공(201 success)
- 통신에 성공할 시, useNavigate를 사용해 로그인 페이지로 이동

#### Shop

[반복되는 데이터 컴포넌트화]
- Shop 페이지에서 perfume 항목이 반복되어 perfume & perfumelist를 컴포넌트화
- 백엔드에서 Mock data를 받아와 fetch 함수로 호출한 후, map 함수를 사용해 반복해서 UI 설정

[상품 카테고리화]
- Shop 페이지를 카테고리화 하고 프론트 & 백 객체 배열 데이터에 [All, 시트러스, 플로럴, 우디, 머스크]에 해당하는 tags를 넣어 matching 되는 tags의 카테고리를 filter 함수로 호출
- 백엔드와 실제 통신해 shop main page 전체 데이터 호출, 각 카테고리를 클릭했을 때 해당 tags에 맞는 항목 재렌더링


#### Detail

[params를 이용한 동적 url]

- Shop page에서든 Survey page에서든 선택한 item 의 id 값을 토대로 화면이 다른 정보들로 렌더링이 되어야 함.
- useParams를 사용하여 선택된 상품의 id 값에 맞춰서 서버에 다르게 요청을 할 수 있도록 구현


[slides 이미지 구현]

- 상품들의 이미지 파일들을 라이브러리 없이 slide 형태를 구현하였음. 
- index를 설정하여 이미지들의 index값에 맞춰서 이미지들의 px 만큼 클릭시 이동하여 선택된 index값의 이미지만 보여지게 구현.


[장바구니에 담을 객체 수량 변경]

- shop page나 survey page를 통해서 받아오는 상품 객체 값의 수량을 변경하여 변경된 객체를 만들어야 함.
- 장바구니에 담기를 클릭하였을 때 백엔드에 보내질 수 있도록 객체를 state 변수인
  setItemInfo 를 통해 업데이트하여 전송하게 만듬.


#### Cart

[delete 메서드]

- fetch를 이용하여 서버에 선택된 item의 id 값을 받아와서 그 id 값의 맞춰 method:DELETE를 이용하여 서버 상에서도 DELETE를 시킵니다.


[부분 선택, 전체 선택]

- 전체 선택을 통해 장바구니에 담긴 모든 상품들의 checked를 true , false로 변경을 하려고 함.
- 선택된 전체 선택의 target.checked의 값을 모든 list 들의 checked의 값을 target.checked의 값을 넣어 변경이 되도록 작성하였음.


[장바구니 수량 변경]
- 이또한 내가 선택한 객체의 id값을 받아와 그것에 맞추어 선택된 값들의 수량이 변경이 될 수 있도록 만들어야 함.
- map 함수를 사용하여 받아온 id의 값과 listItem의 id 값이 일치하면 quantity를 변경할 수 있도록 구성함.

<br>

*아래 Reference 부분은 README.md에 꼭 포함되어야 하는 내용입니다*

## Reference

- 이 프로젝트는 [Paffem] (https://paffem.me/) 사이트를 참조하여 학습목적으로 만들었습니다.
- 실무수준의 프로젝트이지만 학습용으로 만들었기 때문에 이 코드를 활용하여 이득을 취하거나 무단 배포할 경우 법적으로 문제될 수 있습니다.
- 이 프로젝트에서 사용하고 있는 사진 대부분은 위코드에서 구매한 것이므로 해당 프로젝트 외부인이 사용할 수 없습니다.
