# Team project ewha

<br>

> html, Vanilla JS를 이용한 이화여대 마크업 홈페이지입니다.
>
> [배포링크](https://chugyeong.github.io/Ewha/pc/)
>
> 디자인 및 이미지 참고 [이화여대](https://www.ewha.ac.kr/ewha/index.do)

<br>

## 1. 기술 스택

<br>

<img src="https://img.shields.io/badge/html5-E34F26?style=for-the-badge&logo=html5&logoColor=white"><img src="https://img.shields.io/badge/css-1572B6?style=for-the-badge&logo=css3&logoColor=white"><img src="https://img.shields.io/badge/javascript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black">

<br>

## 2. 팀 소개

<br>

| [김기철](https://github.com/habi-er) | [이원철](https://github.com/wonchuring/) | [정종우](https://github.com/honeypunch97) | [추경](https://github.com/ChuGyeong) |
| :----------------------------------: | :--------------------------------------: | :---------------------------------------: | :----------------------------------: |
|                  FE                  |                    FE                    |                    FE                     |                  FE                  |
|           로그인/회원가입            |                헤더/푸터                 |                   메인                    |               학교연혁               |
|               시설안내               |                 공지사항                 |                   대학                    |                총장실                |
|               학생활동               |                 이화뉴스                 |                  대학원                   |               연구성과               |
|             축제/이벤트              |                 입학안내                 |                                           |               산업협력               |

<br>

## 3. 폴더구조

<br>

```
EWha
 ┣ admission_education
 ┃ ┗ admissions_information.html
 ┣ css
 ┃ ┣ reset.css
 ┃ ┗ style.css
 ┣ introduction_to_univ
 ┃ ┣ president’s_office.html
 ┃ ┗ university_history.html
 ┣ js
 ┃ ┗ main.js
 ┣ login_and_signup
 ┃ ┣ login.html
 ┃ ┗ signup.html
 ┣ research_industry
 ┃ ┣ industry_cooperation.html
 ┃ ┗ research_achievement.html
 ┣ univ_graduate
 ┃ ┣ graduate.html
 ┃ ┗ university.html
 ┣ univ_life
 ┃ ┣ facility_information.html
 ┃ ┣ festival_event.html
 ┃ ┗ student_activities.html
 ┣ univ_news
 ┃ ┣ ewha_News.html
 ┃ ┗ notice.html
 ┗ index.html
```

<br>

## 4. 프로젝트 일정

<br>

-  2023.04.28~2023.05.01 사이트 선정 및 프로젝트 기획
-  2023.05.02~2023.05.17 홈페이지 구현
-  2023.05.17~2023.05.30 모바일 작업 및 배포
   ​
   <br>
   ​

## 5. 사이트 미리보기

<br>

## 6. 주요 기능

<br>

> 상세 코드는 [바로가기](https://github.com/ChuGyeong/Ewha/blob/main/pc/js/main.js)에서 확인할 수 있습니다.
> ​

<br>

<details>
<summary>메인</summary>

<br>

```js

```

설명

```js

```

설명

<br>

</details>

<details>
<summary>학교소개</summary>
​​
<br>

## **학교연혁**

<br>

### **탭 클릭 이벤트 리스너 및 탭 내용 표시/숨김**

```js
$universityHistoryTab.forEach(item => {
   item.addEventListener('click', () => {
      $universityHistoryTab.forEach(clickTab => {
         clickTab.classList.remove('on');
      });
      item.classList.add('on');
   });
});

$universityHistoryTab[0].addEventListener('click', () => {
   $universityHistoryYHSE.style.display = 'block';
   $universityHistoryYS.style.display = 'none';
});
$universityHistoryTab[1].addEventListener('click', () => {
   $universityHistoryYHSE.style.display = 'none';
   $universityHistoryYS.style.display = 'block';
});
```

첫 번째 탭($universityHistoryTab[0]) 클릭 시, $universityHistoryYHSE 내용은 표시되고 universityHistoryYS 내용은 숨겨집니다. 이 코드의 주요 기능은 사용자가 탭을 클릭하면 해당 탭에 대한 내용을 표시하고 다른 탭의 내용을 숨기는 것입니다.

<br>

## **총장실**

<br>

### **비주얼 이미지 슬라이드**

```js
$presidentsSlide.style.transition = '0.5s';
$presidentsSlide.style.left = `${presidentsOfficeCurrent * -100}%`;
$presidentsOfficeBtn[presidentsOfficeOld].classList.remove('on');
$presidentsOfficeBtn[presidentsOfficeCurrent].classList.add('on');

if (presidentsOfficeCurrent < $presidentsSlideList.length - 1) {
   presidentsOfficeCurrent++;
} else {
   presidentsOfficeCurrent = 0;
}
visual();
```

슬라이드를 변경하고 적절한 버튼을 활성화시키는 역할을 합니다.  
_0.5s_: 슬라이드 전환 애니메이션 시간을 결정합니다.  
left: 어떤 슬라이드가 화면에서 보여질지 결정합니다. left 값이 변경되면 각 슬라이드의 위치가 바뀌고 보여지는 슬라이드 갱신됩니다.  
그 다음 활성화된 슬라이드 버튼의 상태를 변경합니다. 이전 버튼의 클래스는 remove를 사용해 on 클래스 제거하고, 현재 버튼은 add를 사용해 on 클래스를 추가합니다.

슬라이드 인덱스 값을 증가시키고, 마지막 슬라이드까지 진행한 경우 0으로 재설정되어 첫 번째 슬라이드로 돌아갑니다. 그리고 visual 함수를 호출해 슬라이드 변경이 수행됩니다.

### **이벤트 리스너 및 자동 롤링 설정**

```js
$presidentsOfficeBtn.forEach((item, idx) => {
  item.addEventListener("click", () => {
    ...
  });
});
presidentsOfficeTimeID = setInterval(rolling, 3000);
```

해당 코드는 각 버튼에 클릭 이벤트 리스너를 설정해 수동으로 슬라이드를 변경하게 합니다. 클릭된 버튼의 인덱스 값을 바탕으로 슬라이드를 업데이트하고, 자동 롤링은 잠시 중지하고 다시 시작됩니다. 자동 롤링은 3초 간격으로 설정됩니다.

<br>

</details>
<details>
<summary>연구산학</summary>
​
<br>

## 연구성과

<br>

### **이미지 리스트 클릭 이벤트 리스너**

```js
$researchAchievementAchLi.forEach((item, idx) => {
   item.addEventListener('click', () => {
      $researchAchievementAchLi.forEach(AchLi => {
         AchLi.classList.remove('on');
         AchLi.style.backgroundImage = 'none';
      });
      item.classList.add('on');
      $researchAchievementAchLiImg[
         idx
      ].style.backgroundImage = `url(../images/research_industry/research_achievement/research_achievement_${researchAchievementAchImgType[idx]})`;
   });
});
```

배열의 각 이미지 리스트에 클릭 이벤트 리스너를 추가하여 활성화 용도의 클래스(on) 및 배경 이미지를 변경합니다.

### **스크롤 이벤트**

```js
window.addEventListener('scroll', () => {
   window.scrollY >= $researchAchievementAchBox.offsetTop
      ? ($researchAchievementTopBtn.style.display = 'block')
      : ($researchAchievementTopBtn.style.display = 'none');
});
```

창(window) 스크롤 이벤트 따라 "scrollTop" 버튼이 나타나거나 사라집니다. 스크롤 이벤트가 일어나면 $researchAchievementAchBox 요소의 상단 위치값을 기준으로 맨 위로 이동하는 버튼을 표시 또는 숨깁니다.

<br>

## 산업협력

<br>

### **이미지 롤링 슬라이더**

```js
const iacgVisRolling = () => {
   if (iacgVisCnt >= iacgVisLength) {
      iacgVisCnt = 0;
   }
   $iacgVisList.forEach((item, idx) => {
      item.style.display = 'none';
   });
   $iacgVisList[iacgVisCnt].style.display = 'block';
};

setInterval(() => {
   iacgVisCnt++;
   iacgVisRolling();
}, 3000);
```

iacgVisRolling 함수는 이미지 롤링을 담당하는 함수입니다. setInterval 사용하여 3초마다 한 번씩 자동으로 이동합니다.

### **버튼 클릭 이벤트 리스너**

```js
$iacgVisBtnPrev.addEventListener('click', () => {
   iacgVisCnt--;
   if (iacgVisCnt < 0) {
      iacgVisCnt = iacgVisLength - 1;
   }
   iacgVisRolling();
});

$iacgVisBtnNext.addEventListener('click', () => {
   iacgVisCnt++;
   if (iacgVisCnt >= iacgVisLength) {
      iacgVisCnt = 0;
   }
   iacgVisRolling();
});

$iacgVisBtnPause.addEventListener('click', () => {
   if (iacgVisPaused) {
      iacVisTimeID = setInterval(() => {
         iacgVisCnt++;
         iacgVisRolling();
      }, 3000);
      $iacgVisBtnPause.innerText = '일시정지';
      iacgVisPaused = false;
   } else {
      clearInterval(iacVisTimeID);
      $iacgVisBtnPause.innerText = '재생';
      iacgVisPaused = true;
   }
});
```

이전 버튼과 다음 버튼은 이미지를 이전, 다음으로 이동하게 하며, 재생/일시정지 버튼은 이미지 롤링의 자동 이동을 시작/중지합니다.

### **메뉴 선택에 따른 리스트 출력**

```js
const iacgPlazaMenuMake = title => {
   let html = '';
   iacgData[title].forEach(item => {
      html += `<li>${item}</li>`;
   });
   $iacgPlazaList.innerHTML = html;
};

$iacgPlazaMenu.forEach((item, idx) => {
   item.addEventListener('click', e => {
      iacgPlazaMenuMake(e.target.innerText);
   });
});
```

iacgPlazaMenuMake 함수는 인수로 받은 타이틀에 따라 해당하는 데이터를 이용하여 리스트를 생성합니다. item.addEventListener를 사용하여 각 메뉴 항목에 클릭시 리스트를 출력하는 로직을 추가합니다.

### **리스트 이전/다음 버튼 클릭 이벤트 리스너**

```js
$iacgPlazaMenuPrev.addEventListener('click', e => {
   // (생략) 이전 버튼 클릭 로직
});
$iacgPlazaMenuNext.addEventListener('click', e => {
   // (생략) 다음 버튼 클릭 로직
});
```

리스트 이전 버튼과 다음 버튼에 이벤트 리스너를 추가하여 클릭할 때 리스트를 이전 또는 다음 항목으로 이동하게 합니다.

<br>

</details>
