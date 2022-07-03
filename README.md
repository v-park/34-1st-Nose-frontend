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
- [슬라이드,캐러셀 이미지 구현] 좌,우 버튼 눌렀을 때, 여러장의 이미지가 한장씩 보이도록 구현했습니다. width : 100%, 100vw를 구현하여 반응형 웹페이지가 되도록 구현했습니다.
- [링크관리] 제품교환 서비스, Shop, perfumeTeller,자세히보기, 상품리뷰 등 클릭시 페이지 이동을 구현했습니다.

#### Survey
-[중첩라우팅 구현] Router.js 에서 Survey 컴포넌트에 Survey/* 를 부여하여 Survey/ 뒤에 붙는 url값은 모두 중첩 라우팅을 구현한 Survey.js 파일에서 참조하도록 하였습니다.
- SurveyName.js 에서 유저로부터 받은 name을 SuveyResult.js 에서 보이도록 구현했습니다. QueryString을 통해 데이터를 넘겨주었습니다.
- SuveyName 뿐만 아니라, 다른 페이지에서도 설문을 통해 받은 데이터값을 QueryString으로 SuveyResult 까지 전달하도록 구현했습니다. 

#### Nav/Footer
- [Nav - 스크롤 이벤트 구현] window에 EventListener를 부여하여 scrollY, scrollTop 값을 받도록 하고, 그 값이 >5 일때 색이 반전되도록 구현했습니다.
- [Nav - Modal 구현] openModal(boolean) state로 mouseOver 했을 때, 모달이 열리도록 구현했습니다.

#### Login

#### Signup


#### Shop

#### Detail

#### Cart
<br>

*아래 Reference 부분은 README.md에 꼭 포함되어야 하는 내용입니다*

## Reference

- 이 프로젝트는 [Paffem] (https://paffem.me/) 사이트를 참조하여 학습목적으로 만들었습니다.
- 실무수준의 프로젝트이지만 학습용으로 만들었기 때문에 이 코드를 활용하여 이득을 취하거나 무단 배포할 경우 법적으로 문제될 수 있습니다.
- 이 프로젝트에서 사용하고 있는 사진 대부분은 위코드에서 구매한 것이므로 해당 프로젝트 외부인이 사용할 수 없습니다.
