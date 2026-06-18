# 📋 기말고사 실습 지침서

**과목:** 웹프로그래밍
**시간:** 6시 00분
**배점:** 총 80점

---

## 🎯 실습 목표

HTML, CSS, JavaScript의 핵심 개념을 종합적으로 활용하여 **이벤트 관리 앱**을 구현합니다.

---

## 📁 제공된 파일

```
starter-template/
├── index.html      # ⭐ HTML 구조 (1단계 작성 영역)
├── style.css       # ⭐ CSS 스타일 (2, 6단계 작성 영역)
├── script.js       # ❌ 완전히 비어있음 (3, 4, 5, 7단계 작성)
└── INSTRUCTIONS.md # 📖 이 파일 (전체 지침서)
```

---

## ⚠️ 제약 사항

1. **Vanilla JavaScript만 사용**
   - React, Vue, jQuery 등 사용 불가
   - `import` / `export` 사용 불가
   - `alert()` 사용 불가

2. **인라인 코드 작성 금지**
   - HTML에 `onclick=""` 작성 금지
   - HTML에 `style=""` 작성 금지
   - JavaScript는 `script.js`에만 작성

3. **파일 추가/삭제 금지**
   - 새로운 파일 생성 금지
   - 기존 파일 삭제 금지

---

## 📝 단계별 구현 가이드

###  전체 단계 구조

| 단계 | 내용 | 배점 | 작업 파일 | 완성 테스트 |
|------|------|------|----------|-------------|
| **1단계** | HTML 폼 구조 작성 | 15점 | index.html | 브라우저에서 폼 표시 확인 |
| **2단계** | CSS 버튼 스타일 작성 | 5점 | style.css | 버튼 스타일 및 hover 효과 확인 |
| **3단계** | JavaScript: DOM 선택 + 이벤트 리스너 | 10점 | script.js | 콘솔에서 DOM 요소 확인 |
| **4단계** | JavaScript: 유효성 검사 + 에러 처리 | 8점 | script.js | 빈 입력 시 에러 메시지 확인 |
| **5단계** | JavaScript: 카드 생성 + 날짜 변환 | 12점 | script.js | 카드가 화면에 추가됨 |
| **6단계** | CSS Grid + 반응형 웹 | 14점 | style.css | 화면 너비 조절 시 레이아웃 변화 확인 |
| **7단계** | JavaScript: 이벤트 위임 + 삭제/수정 | 16점 | script.js | 삭제/수정 버튼 동작 확인 |

---

## 🥇 1단계: HTML 폼 구조 작성 (15점)

### 작업 파일: `index.html`
### 작업 위치: `<!-- [1단계 학생 작성 영역] -->` 주석 아래

### 작성해야 할 내용:

```html
<form id="eventForm">
    ...
</form>
```

###  완성 테스트:
- 브라우저에서 `index.html` 열기
- 폼과 입력창, 버튼이 올바르게 표시되는지 확인
- 제목과 날짜에 빨간색 `*` 표시가 있는지 확인

###  배점 기준:
- form 태그 올바르게 작성: 3점
- 제목 입력창 올바르게 작성: 3점
- 날짜 입력창 올바르게 작성: 3점
- 설명 입력창 올바르게 작성: 3점
- 등록 버튼 올바르게 작성: 3점

---

## 🥈 2단계: CSS 버튼 스타일 작성 (5점)

### 작업 파일: `style.css`
### 작업 위치: `/* [2단계 학생 작성 영역] */` 주석 아래

### 작성해야 할 내용:

```css
.btn-primary {
    ...
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    cursor: pointer;
    transition: transform 0.2s, box-shadow 0.2s;
}

.btn-primary:hover {
    transform: translateY(-2px);
    box-shadow: 0 5px 15px rgba(102, 126, 234, 0.4);
}
```

###  완성 테스트:
- 예시 페이지의 모습대로 구현
- 버튼의 폭은 부모 화면에 완전히 꽉 차게 만들고, 위아래 내부 여백을 14px 정도로 두툼하게 주어 사용자가 터치하기 수월하도록 넉넉한 영역을 확보하세요.
브라우저 기본 테두리는 깔끔하게 없애주는 대신, 딱딱한 직각 느낌이 나지 않도록 모서리를 부드럽게 깎아줍니다. 버튼 안의 메시지가 명확하게 눈에 띄도록 글자 크기는 16px로 맞추고, 두께는 굵게(600) 처리하여 본문과 확실히 차별화되도록 강조하세요.

###  배점 기준:
- 기본 스타일 올바르게 작성: 5점


---

## 🥉 3단계: JavaScript DOM 선택 + 이벤트 리스너 (10점)

### 작업 파일: `script.js`
### 작업 위치: `// [3단계 문제]` 주석 아래

### 작성해야 할 내용:

1. **DOM 요소 선택**
   ```javascript
   const eventForm = document.getElementById('eventForm');
   const titleInput = document.getElementById('title');
   const dateInput = document.getElementById('date');
   // ...
   ```
* HTML에 정의된 6개의 요소(`#eventForm`, `#title`, `#date`, `#description`, `#eventsList`, `#errorMessage`)를 각각의 **ID 값을 사용해 자바스크립트 변수로 조회·선택**할 것

2. **폼 제출 이벤트 리스너**
   ```javascript
   eventForm.addEventListener('submit', function(event) {
       event.preventDefault(); // 폼 기본 제출 방지
       // 입력 값 가져오기
       // 유효성 검사
       // 카드 생성
   });
   ```
* 폼 요소(`#eventForm`)에 사용자가 등록을 시도할 때 발생하는 **`submit` 이벤트 리스너를 등록**할 것
* 폼 제출 시 브라우저가 자동으로 페이지를 새로고침하는 기본 동작을 가장 먼저 차단할 것
* 각 입력 필드로부터 사용자가 입력한 **값(`value`)을 추출**할 것
* 이때 제목(`title`)과 설명(`description`) 데이터는 문자열 앞뒤의 불필요한 공백을 모두 제거하여 변수에 할당할 것

3. **조건부 로직 및 후처리 기능 실행**
 - 별도로 구현된 유효성 검사 함수(`validateForm`)에 제목과 날짜를 전달하여 **검증 결과가 통과(`true`)인 경우에만 다음 로직을 수행**할 것
 - 조건 만족 시, 화면에 새로운 카드를 띄우는 함수(`addEventCard`)를 호출하고 폼 안의 모든 입력 필드를 깨끗하게 초기화(`reset`)할 것


###  완성 테스트:
- 브라우저 개발자 도구(F12) 열기
- Console 탭에 다음 입력 후 엔터:
  ```javascript
  console.log(eventForm, titleInput, dateInput);
  ```
- DOM 요소들이 올바르게 선택되는지 확인

###  배점 기준:
- DOM 요소 올바르게 선택: 5점
- 이벤트 리스너 올바르게 작성: 5점

---

## 4단계: JavaScript 유효성 검사 + 에러 처리 (8점)

### 작업 파일: `script.js`
### 작업 위치: `// [4단계 문제]` 주석 아래

### 작성해야 할 내용:

1. **유효성 검사 함수**
    ```javascript
    function validateForm(title, date) {
        // 제목 비어있으면 false
        // 날짜 비어있으면 false
        // 유효하면 true
    }

    function showError(message) {
        ...
    }

    function hideError() {
        ...
    }

   ```


###  완성 테스트:
- 제목을 비워두고 제출 클릭 → "제목을 입력해주세요." 메시지 표시
- 날짜를 비워두고 제출 클릭 → "날짜를 선택해주세요." 메시지 표시
- 에러 메시지가 빨간색 박스에 흔들리는 애니메이션으로 표시되는지 확인

###  배점 기준:
- validateForm 함수 올바르게 작성: 5점
- showError 함수 올바르게 작성: 1.5점
- hideError 함수 올바르게 작성: 1.5점

---

## 5단계: JavaScript 카드 생성 + 날짜 변환 (12점)

### 작업 파일: `script.js`
### 작업 위치: `// [5단계 문제]` 주석 아래

### 작성해야 할 내용:

1. **카드 생성 함수**
   ```javascript
   function addEventCard(title, date, description) {
       // createElement로 카드 생성
       // appendChild로 DOM에 추가
   }

    function formatDate(dateString) {
        const date = new Date(dateString);
        const year = date.getFullYear();
        const month = date.getMonth() + 1;
        const day = date.getDate();
        return `${year}년 ${month}월 ${day}일`;
    }
    ```

###  완성 테스트:
- 폼에 내용을 입력하고 제출
- 카드가 화면에 추가되는지 확인
- 날짜가 "2026년 6월 20일" 형식으로 표시되는지 확인
- "등록된 이벤트가 없습니다." 메시지가 사라지는지 확인

###  배점 기준:
- addEventCard 함수 올바르게 작성: 10점

---

## 6단계: CSS Grid + 반응형 웹 (14점)

### 작업 파일: `style.css`
### 작업 위치: `/* [6단계 문제] */` 주석 아래

### 작성해야 할 내용:

* **기본 컨테이너 설정 (`.container`)**
* 콘텐츠 전체를 감싸는 컨테이너의 최대 너비(`max-width`)를 `900px`로 제한하여 대형 화면에서도 본문 영역이 과도하게 늘어나지 않도록 할 것


* **기본 카드 목록 레이아웃 (`.events-list`)**
* 이벤트 카드 목록 영역에 **CSS Grid** 레이아웃을 적용할 것
* 카드 간의 위아래, 좌우 간격을 `20px`로 설정할 것
* 데스크톱 및 넓은 화면 환경에서 부모 너비에 맞춰 열(Column)의 개수가 자동으로 늘어나거나 줄어들도록 배치하되, 각 카드의 최소 너비는 **`280px`**, 최대 너비는 남아있는 비율만큼 균등 분배되도록 설정할 것


* **태블릿 환경 반응형 대응 (브레이크포인트: 데스크톱 이하 ~ `768px`)**
* 미디어 쿼리를 사용하여 뷰포트 가로 너비가 **`768px` 이하**가 될 때의 스타일을 정의할 것
* 화면이 좁아짐에 따라 카드 목록 내부 요소들의 최소 너비를 기존 `280px`에서 `240px`로 축소 조정하여 레이아웃 깨짐을 방지할 것


* **모바일 환경 반응형 대응 (브레이크포인트: `480px` 이하)**
* 미디어 쿼리를 사용하여 뷰포트 가로 너비가 **`480px` 이하**인 초소형 화면 환경의 스타일을 정의할 것
* 가로 폭이 극도로 좁은 모바일 화면에서는 카드 목록이 열 구분 없이 한 줄에 무조건 한 칸씩만 세로로 꽉 차게 나열되도록 행 구조를 단일 열로 강제 고정할 것


###  완성 테스트:
- 브라우저 너비를 조절하면서 카드 레이아웃이 변하는지 확인
- 작은 화면에서는 한 열, 큰 화면에서는 여러 열로 표시되는지 확인

###  배점 기준:
- Grid 레이아웃 올바르게 구현: 7점
- container 너비 수정: 2점
- 반응형 웹 올바르게 구현: 5점

---

## 7단계: JavaScript 이벤트 위임 + 삭제/수정 (16점)

### 작업 파일: `script.js`
### 작업 위치: `// [7단계 문제]` 주석 아래

**이벤트 위임 구현:**

   ```javascript
    eventsList.addEventListener('click', function(event) {
        ...


    });
   ```


###  완성 테스트:
- 카드에 수정/삭제 버튼이 표시되는지 확인
- 삭제 버튼을 클릭하면 카드가 사라지는지 확인
- 수정 버튼을 클릭하면 폼에 내용이 채워지는지 확인
- 마지막 카드를 삭제하면 "등록된 이벤트가 없습니다."가 다시 표시되는지 확인

###  배점 기준:
- 전역 변수 올바르게 선언: 2점
- addEventCard 함수 수정: 4점
- 이벤트 위임 올바르게 구현: 5점
- deleteEvent 함수 올바르게 작성: 2.5점
- editEvent 함수 올바르게 작성: 2.5점

---

### 개발자 도구 사용
- **F12** 또는 **Ctrl+Shift+I** (Windows/Linux)
- **Cmd+Option+I** (Mac)
- **Console** 탭에서 `console.log()` 출력 확인
- **Elements** 탭에서 DOM 구조 확인



**좋은 결과 있으시길 바랍니다! **

시험이 시작되면 지금 바로 `index.html`을 열어서 **1단계부터 순서대로** 진행하세요!
