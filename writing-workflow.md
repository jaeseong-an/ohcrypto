# 오늘의 크립토 원고 작성 규칙

이 문서는 `오늘의 크립토` 발행 원고를 Markdown으로 작성하고, 이후 HTML 발행본으로 옮길 때 따르는 규칙이다.

목표는 단순하다.

- 작성자는 하루치 원고를 언어별 Markdown 파일로 쓴다.
- AI 편집자는 이 규칙을 읽고 현재 HTML 디자인에 맞게 발행본을 만든다.
- 별도 CMS나 편집 프로그램 없이 초기 발행을 운영한다.

## 기본 원칙

하루치 발행호는 언어별 Markdown 파일로 작성한다.

파일 맨 위에는 front matter로 `date`, `lang`, `issue_title`, `issue_description`을 적는다.

```md
---
date: 2026-05-26
lang: ko
issue_title: 바람잘 날 없는 디파이
issue_description: Safe 지갑 외부모듈 해킹과 StablR 디페그까지. 디파이가 아직 실험장이라는 사실을 보여준 하루.
---
```

`issue_title`은 발행호 전체 제목이다.

`issue_description`은 발행호 전체를 설명하는 짧은 문장이다.

이 둘은 본문 꼭지 제목이 아니라, 아카이브 카드와 발행호 메타 정보에 사용한다.

영어 원고도 같은 구조를 쓴다.

```md
---
date: 2026-05-26
lang: en
issue_title: No Quiet Days in DeFi
issue_description: A hacked external module on a Safe wallet, the StablR depeg, and another reminder that DeFi is still an experimental field.
---
```

## 파일 구조

루트에는 방문자가 직접 들어가는 주요 페이지를 둔다.

```txt
index.html
oh-archive.html
oh-defi.html
oh-decentralization.html
```

`index.html`은 오늘의 크립토 최신호다.

`oh-archive.html`은 오늘의 크립토 지난 호 목록이다.

실제 지난 호 HTML은 `oh-archive/` 폴더에 보존한다.

```txt
oh-archive/
  001_260526.html
```

오늘의 크립토 발행 원고와 대표 이미지는 아래 구조로 둔다.

```txt
today_in_crypto/
  YYMMDD/
    today in crypto_ISSUE_YYMMDD(ko).md
    today in crypto_ISSUE_YYMMDD(en).md
    today-in-crypto-YYMMDD(light).png
    today-in-crypto-YYMMDD(dark).png
```

예:

```txt
today_in_crypto/
  260526/
    today in crypto_1_260526(ko).md
    today in crypto_1_260526(en).md
    today-in-crypto-260526(light).png
    today-in-crypto-260526(dark).png
```

폴더명은 `today_in_crypto`를 표준으로 쓴다.

같은 날짜 폴더 안의 대표 이미지는 다음 두 곳에 사용한다.

- 오늘의 크립토 본문 상단 대표 이미지
- 아카이브 카드 중앙 이미지

## 대표 이미지 규칙

각 발행호는 가능하면 라이트모드용 이미지와 다크모드용 이미지를 함께 둔다.

파일명 끝에 `(light)`와 `(dark)`를 붙인다.

예:

```txt
today-in-crypto-260526(light).png
today-in-crypto-260526(dark).png
```

HTML에서는 `<picture>` 또는 CSS `prefers-color-scheme`을 사용해 사용자의 OS 설정에 맞는 이미지를 보여준다.

라이트모드:

```txt
today-in-crypto-YYMMDD(light).png
```

다크모드:

```txt
today-in-crypto-YYMMDD(dark).png
```

다크모드 이미지가 없는 경우에는 라이트모드 이미지를 fallback으로 사용한다.

## 콘텐츠 라인 구조

이 사이트에는 여러 콘텐츠 라인이 있을 수 있다.

`오늘의 크립토`, `오!디파이`, `오!탈중앙`은 서로 연결될 수 있지만, 같은 원고를 자동으로 공유하거나 분류해 모으는 관계가 아니다.

각 라인은 별도 원고 폴더와 별도 발행 흐름을 가진다.

### 오늘의 크립토

`today_in_crypto/`는 매일 크립토 뉴스 큐레이션 발행용이다.

```txt
today_in_crypto/
  YYMMDD/
    today in crypto_ISSUE_YYMMDD(ko).md
    today in crypto_ISSUE_YYMMDD(en).md
    today-in-crypto-YYMMDD(light).png
    today-in-crypto-YYMMDD(dark).png
```

### 오!디파이

`oh_defi/`는 디파이 구조, 프로토콜, 금융 메커니즘 해설용이다.

```txt
oh_defi/
  YYMMDD/
    oh defi_ISSUE_YYMMDD(ko).md
    oh defi_ISSUE_YYMMDD(en).md
    oh defi_YYMMDD(light).png
    oh defi_YYMMDD(dark).png
```

### 오!탈중앙

`oh_decentralization/`은 탈중앙 이념, 거버넌스, 1차 문헌, 관련 아젠다 분석용이다.

```txt
oh_decentralization/
  YYMMDD/
    oh decentralization_ISSUE_YYMMDD(ko).md
    oh decentralization_ISSUE_YYMMDD(en).md
    oh decentralization_YYMMDD(light).png
    oh decentralization_YYMMDD(dark).png
```

### 라인 간 연결

각 라인은 필요할 때 서로 링크할 수 있다.

예를 들어 `오늘의 크립토`의 특정 꼭지가 더 깊은 디파이 해설을 필요로 하면 `오!디파이` 글로 링크할 수 있고, 탈중앙 이념이나 거버넌스 논의가 필요하면 `오!탈중앙` 글로 링크할 수 있다.

하지만 `오늘의 크립토`의 꼭지가 자동으로 `오!디파이`나 `오!탈중앙` 목록에 들어가지는 않는다.

각 라인의 목록 페이지는 해당 라인의 원고만 보여준다.

## 제목 규칙

Markdown의 제목 단계는 다음 의미로 사용한다.

```md
# 꼭지 제목
## 본문 소제목
### 본문 하위 소제목
```

### `#` 제목

`#`는 발행호 안의 각 꼭지를 뜻한다.

AI는 `#` 제목을 발견한 순서대로 자동 번호를 붙인다.

- 첫 번째 `#` 제목 → `01`
- 두 번째 `#` 제목 → `02`
- 세 번째 `#` 제목 → `03`

HTML에서는 각 `#` 제목이 하나의 기사 카드 또는 꼭지 제목으로 들어간다.

### `##` 제목

`##`는 꼭지 안의 본문 소제목이다.

HTML에서는 본문 중간의 작은 제목으로 표시한다.

### `###` 제목

`###`는 더 작은 하위 소제목이다.

HTML에서는 `##`보다 낮은 단계의 본문 제목으로 표시한다.

## 목차 규칙

발행본 상단에는 접고 펼칠 수 있는 목차 토글을 둔다.

목차는 Markdown 안의 모든 `#` 제목을 자동으로 모아 만든다.

목차는 기본적으로 열린 상태로 둔다.

예:

```txt
오늘의 목차

01 인하시키려 보낸 망치가, 인상을 압박받는다
02 디파이 메커니즘 해부
03 짧은 소식 묶음
```

목차 항목을 누르면 해당 꼭지로 이동하게 만든다.

한국어 페이지에서는 한국어 `#` 제목을, 영어 페이지에서는 영어 `#` 제목을 목차에 사용한다.

## 본문 규칙

일반 문단은 그대로 본문 문단으로 변환한다.

```md
케빈 워시가 연방준비제도 의장으로 취임했다. 하지만 그가 처음 마주한 시장은 예상보다 훨씬 복잡하다.
```

## 인용 규칙

인용문은 Markdown blockquote를 사용한다.

```md
> 워시는 "엄격하게 독립적인" 의장이 되겠다고 말했다.
> 출처: BeInCrypto
```

AI는 이를 HTML의 `blockquote`로 변환한다.

출처가 있으면 `cite` 형태로 정리한다.

## 관련 링크 규칙

관련 링크는 각 꼭지의 참고 자료 묶음으로 작성한다.

한국어 원고에서는 참고 자료 묶음 앞에 `##### 참고`를 쓴다.

영어 원고에서는 참고 자료 묶음 앞에 `##### source`를 쓴다.

그 아래에는 `+ 설명: URL` 형식으로 링크를 적는다.

```md
##### 참고

+ 트럼프의 압박 강도: https://finance.yahoo.com/example
+ 전임자 동석의 기이함: https://www.cbsnews.com/example
```

AI는 `##### 참고` 또는 `##### source`부터 다음 제목이 나오기 전까지의 `+` 링크들을 닫힌 토글 박스로 변환한다.

화면에 표시되는 토글 제목은 원고 제목과 다르다.

- 한국어 `##### 참고` → `오늘의 재료`
- 영어 `##### source` → `Today’s Ingredients`

토글 제목 옆에는 작은 요리 재료 느낌의 아이콘을 함께 넣는다.

토글은 기본적으로 닫힌 상태로 둔다.

변환 예:

```html
<details class="references">
  <summary><span class="ref-label">오늘의 재료</span></summary>
  <p class="plus">트럼프의 압박 강도 — <a href="https://finance.yahoo.com/example" target="_blank" rel="noopener">finance.yahoo.com</a></p>
  <p class="plus">전임자 동석의 기이함 — <a href="https://www.cbsnews.com/example" target="_blank" rel="noopener">cbsnews.com</a></p>
</details>
```

링크 텍스트에는 URL 전체보다 도메인 또는 짧은 출처명을 사용한다.

## 코드 규칙

코드는 Markdown fenced code block을 사용한다.

````md
```js
const protocol = "DeFi";
console.log(protocol);
```
````

AI는 이를 다음 HTML 형태로 변환한다.

```html
<pre class="code-box"><code>const protocol = "DeFi";
console.log(protocol);</code></pre>
```

## 언어 규칙

초기에는 한국어 원고를 기준으로 작성한다.

```md
---
date: 2026-05-26
lang: ko
issue_title: 바람잘 날 없는 디파이
issue_description: Safe 지갑 외부모듈 해킹과 StablR 디페그까지. 디파이가 아직 실험장이라는 사실을 보여준 하루.
---
```

영어판은 다음 세 방식 중 하나로 운영할 수 있다.

- 한국어 원고만 먼저 작성하고, 영어판은 나중에 AI와 함께 작성한다.
- 한국어 원고와 영어 원고를 별도 Markdown 파일로 작성한다.
- 한국어 원고와 영어 초안을 함께 제공하고, AI가 영어 발행본을 다듬는다.

현재 추천 방식은 세 번째다.

## 전체 예시

```md
---
date: 2026-05-26
lang: ko
issue_title: 바람잘 날 없는 디파이
issue_description: Safe 지갑 외부모듈 해킹과 StablR 디페그까지. 디파이가 아직 실험장이라는 사실을 보여준 하루.
---

# 인하시키려 보낸 망치가, 인상을 압박받는다

케빈 워시가 연방준비제도 의장으로 취임했다. 하지만 그가 처음 마주한 시장은 예상보다 훨씬 복잡하다.

> 워시는 "엄격하게 독립적인" 의장이 되겠다고 말했다.
> 출처: BeInCrypto

## 왜 이게 중요한가

트럼프는 금리를 내릴 사람을 원했지만, 물가는 오히려 반대 방향을 가리키고 있다.

##### 참고

+ 트럼프의 압박 강도: https://finance.yahoo.com/example
+ 전임자 동석의 기이함: https://www.cbsnews.com/example

# 디파이 메커니즘 해부

프로토콜은 중립적인 코드처럼 보이지만, 실제로는 돈의 흐름을 설계하는 규칙이다.

```js
const collateralRatio = 1.5;
const liquidationPrice = debt * collateralRatio;
```

# 짧은 소식 묶음

오늘 눈에 띈 짧은 소식들을 모았다.
```

## AI 편집자 변환 지침

AI 편집자는 원고를 HTML에 반영할 때 다음을 지킨다.

- `#` 제목을 기준으로 꼭지를 나누고 자동 번호를 붙인다.
- `##`, `###`는 본문 소제목으로 유지한다.
- `>` 인용은 `blockquote`로 변환한다.
- `##### 참고` 아래의 `+ 설명: URL` 묶음은 닫힌 참고 토글로 변환하고, 표시 제목은 `오늘의 재료`로 바꾼다.
- `##### source` 아래의 `+ 설명: URL` 묶음은 닫힌 참고 토글로 변환하고, 표시 제목은 `Today’s Ingredients`로 바꾼다.
- 참고 토글 제목에는 작은 요리 재료 느낌의 아이콘을 함께 넣는다.
- fenced code block은 `.code-box` 스타일을 사용하는 코드 박스로 변환한다.
- 발행본 상단에 `#` 제목 기반의 접이식 목차를 만들고, 기본으로 열린 상태를 유지한다.
- 꼭지 제목은 `<h2><a href="#story-xx">제목</a></h2>` 형태로 만든다. 그래야 제목 hover 시 노란 밑줄 효과가 유지된다.
- 기존 사이트의 언어 토글, 상단 메뉴, 푸터 구조는 유지한다.
- 원고에 없는 내용을 임의로 추가하지 않는다.
- 링크가 있으면 가능한 한 새 탭에서 열리도록 `target="_blank"`와 `rel="noopener"`를 붙인다.
- 내부 페이지 링크는 현재 언어 상태를 유지해야 한다. `?lang=ko` 또는 `?lang=en`을 붙일 수 있다.
- 언어 상태는 URL의 `lang` 파라미터를 우선하고, 가능하면 `localStorage`에도 저장한다.
- EN 상태에서 메뉴 이동 시 다른 페이지도 EN으로 열려야 한다.
- 대표 이미지가 `(light)`와 `(dark)` 두 개 있으면, 발행본과 아카이브 카드 모두 모드에 맞춰 이미지를 전환한다.
- `(dark)` 이미지가 없으면 `(light)` 이미지를 그대로 사용한다.

## 아카이브 카드 규칙

`index.html`은 항상 오늘의 크립토 최신호다.

오늘의 크립토 각 발행호는 `oh-archive/` 폴더에도 보존한다.

보존본 파일명은 `ISSUE_YYMMDD.html` 형식을 쓴다.

예:

```txt
oh-archive/
  001_260526.html
  002_260528.html
```

`oh-archive.html`은 오늘의 크립토 지난 호 목록 페이지다.

`oh-archive.html`의 각 발행호 카드는 원고 front matter와 대표 이미지를 사용해 만든다.

카드 구조:

- 상단 왼쪽: 발행번호
- 상단 오른쪽: 날짜
- 중앙: 대표 이미지. 가능하면 라이트/다크 이미지를 모드에 맞게 전환한다.
- 하단 제목: `issue_title`
- 하단 설명: `issue_description`

아카이브 카드 클릭 시 해당 호 HTML의 최상단으로 이동한다.

아카이브 카드 링크는 반드시 `oh-archive/ISSUE_YYMMDD.html` 형식의 보존본을 가리킨다.

`index.html`은 최신호 진입점이므로 아카이브 영구 링크로 사용하지 않는다.

보존본은 파일 하나에 독립되어 있으므로 `#issue-001` 같은 해시를 붙이지 않는다.

예:

```html
<a class="card" href="oh-archive/001_260526.html">
```

언어 상태 유지를 위해 실제 렌더링 시에는 JS가 `?lang=ko` 또는 `?lang=en`을 붙일 수 있다.
