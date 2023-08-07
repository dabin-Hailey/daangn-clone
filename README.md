## 📌 프로젝트 개요
### 🔗 사이트 URL
* [당근마켓 홈페이지](https://www.daangn.com)
* [데모 사이트](https://delicate-meringue-7c0c2d.netlify.app/)

### 📆 프로젝트 기간
* 2023.07.24 ~ 2023.07.28
* 2023.08.07 (리팩토링)

### 🛠️ 사용한 기술
<img src="https://img.shields.io/badge/html-E34F26?style=for-the-badge&logo=html5&logoColor=white">
<img src="https://img.shields.io/badge/css-1572B6?style=for-the-badge&logo=css3&logoColor=white">
<img src="https://img.shields.io/badge/javascript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black">
<br>

## 📌 프로젝트 내용

### ✅ 당근마켓 선정 이유
* 클론 과제의 주제가 HTML/CSS로 클론코딩하기 였고, 당시 자바스크립트 학습을 막 시작한 단계였기에 최대한 자바스크립트 사용없이 HTML과 CSS만으로 구현할 수 있는 사이트를 찾다보니 당근마켓이 가장 적합하다 생각했다.

### ✅ 구현 사항
* 시멘틱 태그를 사용하고 클래스명 부여 시 BEM 방법론을 적용하여 HTML 문서만으로도 각 요소가 어떤 역할을 하는지 알 수 있도록 가독성을 높였습니다.
* CSS Flex, Grid 를 활용하여 레이아웃을 유연하게 구성하였습니다.
* pseudo-class (hover, nth-child, last-child)를 활용하여 같은 요소라도 요소별로 다른 스타일을 가질 수 있도록 하였습니다.
<br>

## 📌 프로젝트 회고

### 🚫 첫번째 구현 후 아쉬운 점

* 프로젝트를 시작하기 전, 어떤 구조로 구현할지를 미리 생각해보면 좋을 것 같습니다.
  * 직접 손으로 도식화해서 그려보는 방법도 좋고, 대략적으로나마 구조를 미리 생각해두면 고민하는 시간이 조금이나마 줄어들 것같습니다.
  * 구조가 복잡해질수록 div를 남발하기 쉬워집니다.


* BEM 방법론을 사용해보았으나, 클래스명이 점점 길어져서 중간에 변경하였습니다.


* 코드의 재사용성을 높이기 위해 클래스를 적절히 분배하고 그에 맞는 class name을 부여해야 합니다. 중복되는 코드가 많은데도 어떻게 나누어야 좋을지 결정하지 못하고 같은 내용을 반복하여 작성했습니다.


* 너비에 따른 반응형 웹으로 디자인하면 더욱 좋았을 것같습니다.


* 실제 사이트와 최대한 비슷하게 구현하기 위해 노력하기 위해 원본 코드를 참고했습니다.
  - 폰트는 Google Font에서 찾아 최대한 비슷한 폰트를 적용했습니다.
  - 로고의 경우 이미지 파일로 대체할까 했으나 일반 png 파일로 다운받으면 여백이 달라질 것같아 svg 값을 복사해서 만들었습니다.
  - 원본 코드를 참고해 font-size, padding, margin 값을 설정하였습니다.
➡️ 그래서 그냥 따라치기가 아니었나 하는 생각도 약간 들었지만 그 과정에서 몰랐던 속성을 알게 되었고 적용하고 공부해볼 수 있어서 감사한 경험이었습니다.

* 무엇보다 자바스크립트를 아예 사용해보지 못한 부분이 가장 아쉽습니다.
<br>

### 💡 피어 코드리뷰 및 멘토님 피드백을 통해 개선한 점 (리팩토링)

자바스크립트를 통해 동적으로 데이터를 추가해서 html 마크업에 시간을 줄일 수 있다. (= 자바스크립트로 DOM 추가하기)
➡️ 클론코딩 과제 이후 학습한 자바스크립트 내용으로 개선할 수 있는 내용이라 수정해보았다.
<br>

당근마켓 홈페이지의 footer 내용은 아래와 같다.
아래의 내용 중 `footer-bottom-policy` 라고 구역을 나눈 부분의 html 구조가 반복되는 것이 많아 이 부분을 자바스크립트로 작성해보았다.
![](https://velog.velcdn.com/images/mary0393/post/36891677-9166-4232-90fa-a53854c7f8aa/image.png)

> **기존에 html로 작성한 코드 (반복되는 코드)**
```html
<section class="footer-bottom-policy">
  <div class="policy-text">
    <a class="policy-text text-underline" href="https://www.daangn.com/policy/terms" target="_blank">이용약관</a>
  </div>
  <div class="policy-text">
    <a class="policy-text text-underline text-gray" href="https://privacy.daangn.com" target="_blank">개인정보처리방침</a>
  </div>
  <div class="policy-text">
    <a class="policy-text text-underline" href="https://www.daangn.com/policy/location" target="_blank">위치기반서비스 이용약관</a>
  </div>
  <div class="policy-text">
    <a class="policy-text text-underline" href="https://www.daangn.com/wv/faqs/3994" target="_blank">이용자보호 비전과 계획</a>
  </div>
  <div class="policy-text">
    <a class="policy-text text-underline" href="https://www.daangn.com/wv/faqs/9010" target="_blank">청소년보호정책</a>
  </div>
</section>
```

> **자바스크립트로 수정한 코드**
```jsx
//1. 부모 div 선택
const footerPolicyDiv = document.querySelector('.footer-bottom-policy');
>
//2. 반복되는 부분 데이터화
const policyData = [
  {
    href : "https://www.daangn.com/policy/terms",
    content : "이용약관",
    id : 1,
  },
  {
    href : "https://privacy.daangn.com",
    content : "개인정보처리방침",
    id : 2,
  },
  {
    href : "https://www.daangn.com/policy/location",
    content : "위치기반서비스 이용약관",
    id : 3,
  },
  {
    href : "https://www.daangn.com/wv/faqs/3994",
    content : "이용자보호 비전과 계획",
    id : 4,
  },
  {
    href : "https://www.daangn.com/wv/faqs/9010",
    content : "청소년보호정책",
    id : 5,
  },
]
>
//반복문을 통해 policyData를 요소로 만들기
policyData.forEach(data => {
  //policy-text div와 a태그를 만들어 속성을 추가한다.
  const policyTextDiv = document.createElement('div')
  policyTextDiv.classList.add('policy-text')
  const policyTextA = document.createElement('a')
  policyTextA.classList.add('policy-text')
  policyTextA.classList.add('text-underline')
  policyTextA.href = data.href
  policyTextA.textContent = data.content
  policyTextA.target = "_blank"
>
  policyTextDiv.append(policyTextA);
  footerPolicyDiv.append(policyTextDiv);
})
```

- 이 부분을 수정할 때 고려할 점은 반복되는 부분의 데이터를 **배열과 객체를 사용하여 변수로 만들어주는 부분**이다. 아직은 어색하지만 원리를 이해하고 연습해서 이런 방식이 익숙해지도록 해야겠다.
<br>

### 🚫 리팩토링 후 아쉬운 점

1. 멘토님의 피드백을 통해 `footer-bottom-policy` 부분을 JS로 구현해봤는데 모든 태그가 동일한 클래스를 갖고 있지 않고, 한 태그만 따로 갖고 있는 클래스가 있어서 그걸 어떻게 적용시킬 수 있을지 찾다 결국 찾지 못했다. **멘토링 시간에 따로 여쭤보고 추가 내용을 수정할 수 있도록 한다.**
<br>

2. 미디어 쿼리를 사용해서 접속 기기에 따른 반응형 웹 구현하기
- 실제 당근마켓 사이트는 완벽하게 반응형 구조를 적용하고 있지 않았다.
- 너비에 따른 변화가 있는 부분은 nav바와 footer 뿐이었다. 본문이 들어있는 main 섹션은 스크롤바가 생성되며 pc에서와 차이가 없다.
- 그래서 실제 반응형으로 구현된 다른 사이트를 참고하면서 조금 더 학습할 필요가 있다.

3. 여전히 grid는 어렵다...
클론 과정에서 grid 실습해볼때는 괜찮았던 것같은데 막상 또 다시 내용을 훑어보니 과연 내가 알았던게 맞는지 의심될 정도로 또 어색한 사이가 되었다... 꾸준히 복습해서 잊지 않도록 해야겠다.
<br>

## 📌 배운 점

### ✅ outline 속성
: 검색창 클릭했을 때 나타나는 테두리는 border가 아닌 `outline`이다. 따라서 `outline : none;` 으로 해야 선택했을 때 테두리가 없어진다.

### ✅ opacity 속성
: ‘채팅하기’ 버튼에서 hover 하면 background-color만 변경되는게 아니라 버튼 전체적으로 투명도가 씌워짐. `opacity`를 적용한다.

### ✅ will-change 속성
: 요소의 변화를 미리 브라우저에게 알려주어 브라우저가 미리 최적화를 하게 할 수 있는 속성
https://coding-farmer.tistory.com/7

### ✅ text-overflow  속성
: text-overflow는 white-space를 이용해 줄 바꿈을 하지 않을 때 넘치는 텍스트 처리를 어떻게 할 것인지를 처리하는 속성

| 속성 | 설명 |
| --- | --- |
| clip | 넘치는 텍스트를 자름 |
| ellipsis | 말 줄임표로 잘린 텍스트가 있다고 표시 |
