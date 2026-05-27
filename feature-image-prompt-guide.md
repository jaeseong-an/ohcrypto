# 오늘의 크립토 대표 이미지 생성 프롬프트 가이드

이 문서는 `오늘의 크립토` 기사 상단에 들어가는 대표 이미지를 같은 품질과 톤으로 반복 생성하기 위한 가이드다. 새 채팅에서 이미지를 만들 때 이 파일의 내용을 함께 전달하면 된다.

목표는 “1인 미디어가 직접 대충 펜으로 그린 듯한 이미지”다. 그림은 단순하고 허술해 보여도, 기사에서 가장 중요한 생각은 한눈에 보여야 한다.

## 핵심 스타일

- 흰 배경 또는 다크모드용 짙은 배경 위의 단순한 손그림
- 일부러 반듯하지 않은 검은 펜선
- 큰 여백
- 적은 사물 수
- 설명보다 은유
- 귀엽기보다는 건조하고 살짝 웃긴 느낌
- 전문 일러스트레이터의 완성도보다 1인 미디어의 손맛
- 색은 기본적으로 검정과 흰색, 그리고 노란색 `#ffd400` 한 가지 포인트만 사용

참고 톤은 특정 작가의 화풍을 복제하는 것이 아니라 다음 특징만 가져온다.

- 작은 spot illustration처럼 한 장면만 보여준다.
- 말풍선이나 긴 텍스트 없이, 사물의 관계로 의미를 전달한다.
- 선은 약간 삐뚤고 즉흥적이다.
- 과하게 멋있거나 세련되지 않다.
- 여백이 많고 장면은 단순하다.

## 절대 피할 것

- 특정 작가의 이름을 넣고 “그 작가 스타일로” 요청하지 않는다.
- 정교한 벡터 일러스트처럼 보이게 만들지 않는다.
- 3D, 반짝이는 코인, 네온, 사이버펑크, 거래소 광고 같은 크립토 클리셰를 피한다.
- 너무 많은 오브젝트를 넣지 않는다.
- 실제 로고, 브랜드명, 체인 로고를 넣지 않는다.
- 이미지 안에 읽을 수 있는 글자를 넣지 않는다. 문서나 표식은 짧은 구불구불한 선으로 처리한다.
- 캐릭터를 과하게 귀엽게 만들지 않는다.
- 배경 질감, 그림자, 그라데이션, 종이 텍스처를 넣지 않는다.

## 기사에서 뽑아야 하는 것

이미지 생성 전에 원고를 읽고 아래 3가지만 정한다.

1. 이번 글의 핵심 갈등은 무엇인가?
2. 그 갈등을 가장 단순한 사물 은유로 바꾸면 무엇인가?
3. 노란색 포인트는 어디에 둘 것인가?

예시:

- Safe 모듈 악용: 금고 옆에 붙은 작은 모듈이 돈을 빼가는 장면
- 1-of-3 멀티시그 문제: 세 개의 손 중 하나가 조폐기 버튼을 누르는 장면
- 스테이블코인 디페그: 동전이 작은 못 위에서 균형을 잃는 장면
- AI 결제: 작은 로봇 손이 지갑을 들고 결제하는데 뒤에서 권한 스위치가 따라오는 장면
- 탈중앙의 모순: 여러 노드 중 하나가 몰래 왕관과 큰 열쇠를 들고 있는 장면

## 기본 라이트모드 프롬프트

아래 프롬프트에서 대괄호 부분만 기사에 맞게 바꿔 사용한다.

```text
Use case: illustration-story
Asset type: website feature image for a Korean one-person crypto media homepage, 16:9 horizontal hero image

Primary request:
Create a deliberately rough, naive pen doodle for an article about [ARTICLE TOPIC].
The image should look like it was drawn quickly by one person with a black felt-tip pen, not like a polished editorial commission.
It must be simple and slightly awkward, but the central metaphor should be immediately readable.

Scene/backdrop:
Pure white background with lots of empty space.
No paper texture, no shadows, no gradients, no decorative background.

Subject:
Show [ONE SIMPLE METAPHORIC SCENE].
Use only a few objects.
The objects should explain the article’s core idea through their relationship, not through text.
If a paper, screen, contract, label, sign, or document appears, it must contain only loose squiggle marks, not readable words.

Composition:
Horizontal 16:9 composition.
Center the main visual.
Keep the drawing sparse enough to work at homepage size.
Use a single-panel spot illustration feeling.
The scene should feel dryly funny, slightly absurd, and handmade.

Color:
Black uneven ink lines on white.
Use only one restrained flat yellow accent, preferably #ffd400.
The yellow accent should mark the most important object or risk.
Do not add any other accent colors.

Line quality:
Use thick, uneven, imperfect pen lines.
Allow wobbly contours and small inconsistencies.
Avoid smooth vector curves.
Avoid polished, symmetrical, glossy, or corporate-looking illustration.

Tone:
One-person media, rough notebook energy, simple visual joke, understated satire.
Not childish, not cute mascot style, not dramatic, not cinematic.

Avoid:
No readable typography.
No logo marks.
No photorealism.
No 3D.
No gradients.
No shadows.
No texture.
No watermark.
No complex background.
No crypto poster aesthetic.
Do not imitate any named living artist.
```

## 기본 다크모드 프롬프트

라이트모드 이미지를 먼저 만든 뒤, 같은 구도와 서사를 유지하면서 다크모드용으로 변환한다.

```text
Use the light mode image as the direct reference and create a matching dark mode version.

Use case: illustration-story
Asset type: website feature image for dark mode, 16:9 horizontal hero image

Primary request:
Keep the same composition, same objects, same metaphor, and same rough handmade drawing quality as the light mode image.
Convert only the color contrast so it works on a dark website.

Scene/backdrop:
Deep near-black charcoal background, close to #0d0d0d.
Flat background only.
No texture, no gradients, no shadows.

Line art:
Use warm off-white ink lines so the drawing is clearly readable on dark background.
Keep the linework uneven, rough, and hand-drawn.
Do not make it chalky or over-textured.

Color:
Keep the yellow accent as a flat #ffd400 or slightly warmer bright yellow.
The yellow object should match the role it had in the light mode image.
Do not introduce new accent colors.

Subject:
Preserve the same central metaphor: [SAME METAPHORIC SCENE].
No readable text; use only squiggle marks if papers or signs appear.

Avoid:
No glow effects.
No neon.
No gradients.
No realistic lighting.
No polished vector look.
No extra typography.
No watermark.
Do not imitate any named living artist.
```

## 2026-05-26 대표 이미지에 사용한 방향

원고 핵심:

- Safe 모듈 악용
- 외부 모듈이나 권한이 금고의 대리인처럼 행동할 수 있음
- StablR 사고는 스마트컨트랙트 버그보다 키 관리와 거버넌스 실패에 가까움
- 1-of-3 권한 구조에서 하나의 키 또는 손이 너무 큰 힘을 가질 수 있음
- 조폐 권한을 훔쳐 새 돈을 찍어 시장에 던진 것에 가까움

선택한 은유:

- 큰 허가서
- 서명하는 세 개의 손
- 그중 하나는 음흉하거나 악의를 가진 손
- 아래의 노란 금고/조폐 박스
- 박스 안에서 돈이 마구 튀어나옴

라이트모드 프롬프트 예시:

```text
Use case: illustration-story
Asset type: final website feature image for light mode, 16:9 horizontal hero image

Primary request:
Create a deliberately rough, naive pen doodle for a Korean one-person crypto media homepage.
Show a giant permission paper being signed by three hands.
One hand, preferably the right-side hand, should feel subtly malicious and sneaky through its gesture and posture, not scary or realistic.
Below the paper, show a yellow treasury box or minting box with lots of money bursting out: simple hand-drawn coins and bills popping upward and outward from the slot.
The image should suggest that one authorized hand can trigger too much financial power.

Scene/backdrop:
Pure white background with lots of empty space.
No paper texture, no shadows, no gradients, no decorative background.

Subject details:
The paper contains only loose squiggle marks, no readable text.
The yellow box is the main color accent.
The malicious hand is still a simple doodled hand holding a pen, with a sly curved pose or claw-like grip.
The money burst should feel energetic but still sparse and handmade.

Composition:
Horizontal 16:9 composition.
Center the paper and box.
Keep the scene readable at homepage size.
Single-panel spot illustration.

Style constraints:
Deliberately imperfect black felt-tip line quality.
Simple, awkward, humorous, handmade.
Black uneven ink lines plus flat yellow #ffd400 accent only.
No polished vector look, no gradients, no shadows, no texture, no photorealism, no watermark, no extra typography.
Do not imitate any named living artist.
```

다크모드 프롬프트 예시:

```text
Use the light mode image as the direct reference and create a matching dark mode version.

Use case: illustration-story
Asset type: final website feature image for dark mode, 16:9 horizontal hero image

Primary request:
Same composition and storytelling as the light image:
a giant permission paper, three signing hands, one subtly malicious sneaky hand on the right, and a yellow treasury box with coins and bills bursting out.
Convert the color contrast for dark mode.

Scene/backdrop:
Deep near-black charcoal background, close to #0d0d0d.
Clean flat color.

Subject details:
Draw all line art in warm off-white ink so it reads clearly on dark background.
Keep the box as a flat yellow accent, #ffd400 or slightly warmer.
Use no readable text, only squiggle marks on paper.
Preserve the rough doodle handmade look.

Style constraints:
Deliberately imperfect spot illustration.
Uneven pen lines, sparse, simple, humorous.
No gradients, no shadows, no texture, no photorealism, no polished vector look, no watermark, no extra typography.
Do not imitate any named living artist.
```

## 시안 10개를 만들 때 쓰는 프롬프트 구조

대표 이미지 방향을 아직 고르지 못했을 때는 같은 스타일로 은유만 바꿔 10개를 만든다.

```text
Create draft [NUMBER] of 10.

Use case: illustration-story
Asset type: website feature image draft for a Korean one-person crypto media homepage, 16:9 horizontal hero image

Primary request:
Create a deliberately rough, naive pen doodle on a pure white background.
The drawing should be simple and look casually made by one person, but it must clearly express the article’s core idea:
[CORE IDEA].

Subject:
[DISTINCT METAPHOR FOR THIS DRAFT].

Composition:
Centered, sparse, awkward, dryly funny, readable at small homepage size.

Style constraints:
Black uneven felt-tip pen lines.
Lots of white space.
One small flat yellow accent only, #ffd400.
No readable text.
No polished vector look.
No gradients.
No shadows.
No texture.
No photorealism.
No watermark.
Do not imitate any named living artist.
```

## 좋은 은유를 고르는 기준

좋은 대표 이미지는 기사 전체를 다 설명하지 않는다. 하나의 핵심만 고른다.

좋은 은유:

- 금고 옆에 붙은 작은 플러그인 박스가 돈을 가져간다.
- 세 개의 손 중 하나가 조폐 상자를 작동시킨다.
- 동전이 작은 못 위에서 균형을 잃고 있다.
- 로봇 손이 결제하려는데 뒤에 큰 권한 스위치가 따라온다.
- 탈중앙 네트워크 속 한 노드만 왕관과 열쇠를 들고 있다.

나쁜 은유:

- 체인 로고, 코인 로고, 거래 차트, 해커 후드, 서버실을 한꺼번에 넣는다.
- 기사에 나온 모든 사건을 한 이미지에 다 넣는다.
- “DeFi”, “AI Payment”, “Hack” 같은 단어를 이미지 안에 적는다.
- 멋진 금융 광고처럼 보이게 만든다.

## 투명 배경이 필요할 때

최종 선택 후 투명 배경 PNG가 필요하면 바로 투명 배경을 요구하기보다, 배경 제거가 쉬운 플랫 배경으로 먼저 만든다.

```text
Create the same subject on a perfectly flat solid chroma-key background for background removal.
The background must be one uniform color with no shadows, gradients, texture, reflections, floor plane, or lighting variation.
Keep the subject fully separated from the background with crisp edges and generous padding.
Do not use the chroma-key color anywhere in the subject.
No cast shadow, no contact shadow, no reflection, no watermark, and no readable text.
```

단, 현재 홈페이지의 대표 이미지는 라이트모드용 흰 배경과 다크모드용 짙은 배경을 따로 쓰는 방식이 더 자연스럽다. 투명 배경은 같은 이미지를 여러 배경 위에 자유롭게 얹어야 할 때만 만든다.

## 파일명 규칙

대표 이미지는 날짜와 용도를 파일명에 넣는다.

```text
today-in-crypto-YYMMDD-feature-light.png
today-in-crypto-YYMMDD-feature-dark.png
today-in-crypto-YYMMDD-feature-transparent.png
```

예시:

```text
today-in-crypto-260526-feature-light.png
today-in-crypto-260526-feature-dark.png
```

HTML에서는 라이트/다크 이미지를 이렇게 연결한다.

```html
<picture>
  <source srcset="today_in_crypto/260526/today-in-crypto-260526-feature-dark.png" media="(prefers-color-scheme: dark)">
  <img src="today_in_crypto/260526/today-in-crypto-260526-feature-light.png" alt="Hand-drawn permission paper being signed by three hands, with a sneaky hand and money bursting from a yellow treasury box">
</picture>
```

## 최종 점검 체크리스트

- 원고의 핵심이 이미지 하나로 읽히는가?
- 사물이 너무 많지 않은가?
- 이미지 안에 읽을 수 있는 글자가 없는가?
- 노란색 포인트가 하나의 핵심에만 쓰였는가?
- 라이트모드와 다크모드가 같은 구도와 같은 의미를 유지하는가?
- 홈페이지 상단에서 너무 복잡하거나 광고처럼 보이지 않는가?
- “1인 미디어가 직접 그린 듯한 허술함”이 남아 있는가?
