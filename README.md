
<img width="1791" alt="스크린샷 2021-07-02 오후 5 00 12" src="https://user-images.githubusercontent.com/73716178/124345227-a757c000-dc12-11eb-94b0-dc5fb40288c1.png">

# YourHouseToday front-end team 입니다!🏠
아름다운 가구 인테리어 소품들을 판매하고 커뮤니티 기능을 가진 **[오늘의집](https://ohou.se/)** 을 모티브로 하여 '오늘은 너네집'이라는 가상의 브랜드와 기획을 더한 팀 프로젝트

# 프로젝트 소개
초기 세팅부터 전부 직접 구현했으며, 짧은 기간동안 개발에 집중해야 하므로 스토어 기능보다는 집 인테리어 사진을 공유하는 하는 **커뮤니티 기능**을 더 집중화하여
개발 하였습니다.

## 프로젝트 계획 및 기간
📆 2021.6.21 ~ 7.02
- 1st Sprint : 개발환경 초기세팅, 전체 레이아웃, 컴포넌트화
- 2nd Sprint : 컴포넌트 별 기능 구현, 프론트-백 통신, 코드 리팩토링, conflict 수정 작업

# 메인 서비스
1. 카카오 소셜 로그인으로 가입할 수 있습니다.
2. 집 사진과 글을 피드처럼 올릴 수 있습니다.
3. 피드를 필터링, 무한스크롤로 구경할 수 있습니다.
4. 마이페이지에서 내가 올린 사진과 글을 볼 수 있습니다. 

## 페이지별 기능 Demo

### 메인,리스트 페이지
![1](https://user-images.githubusercontent.com/73716178/124347592-649ce480-dc20-11eb-9897-cb7da04ce479.gif)

### Nav바-로그인/회원가입
![2](https://user-images.githubusercontent.com/73716178/124347735-04f30900-dc21-11eb-9e93-8242759a460d.gif)

### 로그아웃/회원가입시 메일
![7](https://user-images.githubusercontent.com/73716178/124348118-1c32f600-dc23-11eb-8f45-cd4136d3c942.gif)

### 글쓰기 페이지
![4](https://user-images.githubusercontent.com/73716178/124347915-f2c59a80-dc21-11eb-958a-5140eb1fc778.gif)

### 마이페이지
![3](https://user-images.githubusercontent.com/73716178/124347813-75018f00-dc21-11eb-8b3c-7ac2ab2f29d0.gif)
![6](https://user-images.githubusercontent.com/73716178/124348042-b9415f00-dc22-11eb-8b35-7d328632a274.gif)

### 게시글 상세페이지
![5](https://user-images.githubusercontent.com/73716178/124347994-6e274c00-dc22-11eb-9b85-8b4db92da361.gif)

### 오늘은 너네집 Demo 유튜브 링크
<a href="https://www.youtube.com/watch?v=Xbwk51T7v9s&ab_channel=%EC%A0%84%EA%B1%B4%EC%9A%B0">
    <img src="http://img.shields.io/badge/-YouTube-FF0000?style=flat&logo=YouTube&link=https://https://www.youtube.com/watch?v=SE_5vtrBrsg/"
        style="height : auto; margin-left : 10px; margin-right : 10px;"/>
</a>

## 구현 기능 상세

### 공통 
- React 기반의 홈페이지 제작
- CRA를 사용한 초기 세팅

### 소셜 로그인 페이지 (김명준) 
- 페이지 이동없는 로그인 modal 창 구현
- Kakao API를 사용하여 Kakao 로그인 및 회원가입 기능 
- 신규회원 닉네임 변경 기능
- 닉네임 중복일 경우, 닉네임 추천 기능 
- 사용자 인증(Authentication) 완료에 따른, Local Storage에서의 access token(JSON Web Tokens) 관리

### 네비게이션 바 (김명준) 
- 공통 Nav UI 구현
- 로그인 상태에 따라 버튼 레이아웃 변경
- Kakao 계정 프로필 이미지를 기본 프로필 사진으로 설정
- 프로필 이미지 클릭시 마이페이지, 로그아웃 선택가능  UI 구현
- Local Storage에서의 토큰의 여부를 통해 로그인 여부 확인
- Local Storage에서 토큰을 삭제로 로그아웃 기능

### 글쓰기 페이지 (김명준) 
- 카테고리 선택 modal 구현 / 컬러 미리보기 기능 구현
- FileReader API를 통해 이미지 업로드 후 미리보기 구현
- 전체 카테고리 유효성검사 (전체 선택시에만 업로드 가능하게 구현)
- FileData API를 통해 백엔드로 사용자가 업로드한 이미지파일을 전송

### 메인,리스트 페이지(전건우)
- fecth를 이용해 백엔드와 통신하여 메인 페이지 데이터 렌더링
- react-router를 사용한 동적 라우팅 (메인 -> 게시글의 상세페이지 이동)
- 메인페이지의 slick 라이브러리를 사용하여 메인페이지 Carousel 구현
- 페이지 스크롤시 제일 아래까지 내려가면 QueryString의 주소를 변경해 데이터를 받아오는 형식의 무한스크롤 구현
- rc-slider라이브러리를 사용하여 양방향 range 기능(평수 필터링버튼) 구현
- 필터된 게시글이 없다면 다른 페이지 렌더링
- QueryString을 사용한 필터 클릭 시 각 버튼에 해당하는 필터된 데이터의 API 주소를 변경해 리랜더링해주는 게시글 필터 구현

### 마이페이지 (전건우)
- 메인페이지에서 받는 데이터를 받아서 데이터 렌더링
- Local Storage의 해당 유저의 토근을 받아와 유저의 올린 사진(게시글)데이터를 렌더링
- 유저가 포스팅한 사진이 없을경우 다른 페이지가 렌더링

### 제품 상세 페이지 (권오현) 
- fecth를 이용해 백엔드와 통신하여 페이지 데이터 렌더링
- 상품 이미지 캐러셀 노출 기능 구현
- 상세설명/정보/리뷰/배송,환불,문의 탭 기능 구현
- 상품 찜하기 기능 구현


## 🛠 사용한 기술

Front-End :<img src="https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=HTML5&logoColor=white"/></a> <img src="https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=React&logoColor=white"/></a> <img src="https://img.shields.io/badge/React_Router-CA4245?style=flat-square&logo=ReactRouter&logoColor=white"/></a> <img src="https://img.shields.io/badge/styled Components-DB7093?style=flat-square&logo=styled-components&logoColor=white"/></a> <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=JavaScript&logoColor=white"/></a>

Back-End : <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=Python&logoColor=white"/></a> <img src="https://img.shields.io/badge/Django-092E20?style=flat-square&logo=Django&logoColor=white"/></a> <img src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=MySQL&logoColor=white"/></a> <img src="https://img.shields.io/badge/JWT-000000?style=flat-square&logo=JSONWebTokens&logoColor=white"/></a> <img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=Docker&logoColor=white"/></a>

## 🛠 사용한 툴
Common : <img src="https://img.shields.io/badge/Slack-4A154B?style=flat-square&logo=Slack&logoColor=white"/></a> <img src="https://img.shields.io/badge/Trello-0052CC?style=flat-square&logo=Trello&logoColor=white"/></a> <img src="https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=GitHub&logoColor=white"/></a> <img src="https://img.shields.io/badge/Git-F05032?style=flat-square&logo=Git&logoColor=white"/></a> <img src="https://img.shields.io/badge/PostMan-FF6C37?style=flat-square&logo=PostMan&logoColor=white"/></a> <img src="https://img.shields.io/badge/Amazon S3-569A31?style=flat-square&logo=AmazonS3&logoColor=white"/></a> <img src="https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=AmazonAWS&logoColor=white"/></a>

## 👥 팀원

- 프론트 : [권오현](https://github.com/im667), [김명준](https://github.com/JOHNKIM-KK), [전건우](https://github.com/fghjjkl32)
- 벡엔드 : [김정연](https://github.com/geekanne), [배찬영](https://github.com/cj4207), [장동국](https://github.com/JangDongGuk)
 (오늘은 너네집 벡앤드팀 [깃허브](https://github.com/wecode-bootcamp-korea/21-2nd-YourHouseToday-backend))

## Reference
이 프로젝트는 [오늘의집](https://ohou.se/) 사이트를 참조하여 학습목적으로 만들었습니다.
프로젝트에 사용한 모든 이미지와 영상은 저작권에 문제가 없는 컨텐츠를 사용하여 만들었습니다.
실무 수준의 프로젝트이지만 학습용으로 만들었기 때문에 이 코드를 활용하여 이득을 취하거나 무단 배포할 경우 법적으로 문제될 수 있습니다.

---
개발 클론이 아닌 '기획 클론'!! 
- 오늘은너네집 프로젝트는 [오늘의집](https://ohou.se/) 클론 프로젝트이지만, 백지 상태에서 구현되었습니다.
개발자의 역할은 기획이 아닌, 기획 의도를 현실로 바꾸는, 기획의 ‘구현’이라 생각합니다.
따라서, 기획 과정을 건너 뛰고 구현에 집중하기 위해  [오늘의집](https://ohou.se/)라는 서비스를 참고한 것일 뿐,
프로젝트의 모든 기능은, 실제 서비스 개발과정과 마찬가지로, 백지 상태에서 구현되었음을 밝힙니다.
