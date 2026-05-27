---
date: 2026-05-26
lang: ko
issue_title: 바람잘 날 없는 디파이
issue_description: Safe 지갑 외부모듈 해킹과 StablR 디페그까지. 디파이가 아직 실험장이라는 사실을 보여준 하루.
---

바람잘 날 없는 디파이 생태계의 소식들에 집중해봤습니다. 어려운 거 같기도 하고, 또 되게 허술한 거 같기도 하고, 미래인 건 분명한 거 같은데 또 막 탈중앙은 무슨 탈중앙이야 싶기도 하고 그러네요잉?

# 모듈 해킹과 인공지능 결제

이더리움과 베이스에서 “SquidRouterModule” 이름의 제3자 Safe 모듈이 악용돼 약 320만 달러가 빠져나간 것으로 보입니다. Squid는 “이 모듈은 우리가 만들거나 배포한 것이 아니고, 이름만 SquidRouterModule일 뿐 핵심 Squid Router 계약과 다르다”고 선을 씨게 그었습니다. 그러거나 말거나. 중요한 지점은 Safe 자체보다 '지갑에 승인된 외부 모듈이 사실상 금고의 대리인처럼 행동할 수 있다'는 점이고, 이 지점에서 해킹이 발견될 수 있다는 점입니다.

이번 Safe 관련 사고의 핵심은 "지갑 자체가 털렸나?"보다 "지갑에 붙인 외부 모듈이 얼마나 큰 권한을 갖고 있었나?"입니다. Safe는 여러 사람이 함께 서명해야 자산이 움직이는 멀티시그 지갑으로 많이 쓰인다네요. DAO나 프로젝트 금고가 자주 사용할 겁니다. 여기에 외부 모듈을 붙이면 특정 작업을 자동화할 수 있습니다. 이를테면 매월 누군가에게 운영비 얼마를 자동으로 보낼 수 있는 거죠? 이런 부분에 대해서 매번 3명이 승인하려면 시간이 오래 걸리고 비효율적일 겁니다. 그래서 Safe에 모듈을 붙여서 '이 모듈은 우리가 허락한 프로그램이니까 이 모듈이 정해진 규칙 안에서 요청하면 매번 3명의 서명을 받지 않아도 Safe 자금을 움직일 수 있게 해줘 아라쮜~?'라고 하는 것입니다.

인공지능이 결제까지 도맡을 세상이 곧 다가온다는 느낌이 든다 아닙니까? Coinbase는 작년 5월에 x402를 소개했습니다. 이는 인공지능 에이전트나 앱이 HTTP 요청 흐름 안에서 스테이블코인으로 API, 서비스, 콘텐츠 비용을 지불할 수 있게 하는 결제 프로토콜입니다. 이후 Cloudflare와의 x402 Foundation, Linux Foundation 편입, AWS Bedrock AgentCore Payments 프리뷰 등으로 이어지며, 지금은 ‘AI 에이전트가 돈을 쓰는 인터넷’의 초기 표준 후보 중 하나가 되고 있습니다. 앞에서 해킹당한 모듈이 인공지능이 되는 세상도 상상해볼 수 있을 거 같은데, 권한을 얼만큼 주고 어떻게 다양한 상황에 대비할 수 있을지 앞으로 지켜봐야할 거 같습니다. 아! 흥미진진해라~!!

##### 참고

+ Safe 모듈 익스플로잇 보도: https://www.theblock.co/post/402487/we-dont-know-who-deployed-this-squid-distances-itself-from-3-2-million-third-party-module-exploit
+ Cointelegraph의 Safe·Squid 정리: https://cointelegraph.com/news/squid-safe-labs-third-party-module-3-2-million-exploit
+ Safe 공식 문서 - 모듈이란 무엇인가: https://docs.safe.global/advanced/smart-account-modules
+ Coinbase의 x402 최초 소개: https://www.coinbase.com/en-it/developer-platform/discover/launches/x402
+ Cloudflare와 Coinbase의 x402 Foundation 발표: https://blog.cloudflare.com/x402
+ AWS Bedrock AgentCore Payments 프리뷰: https://aws.amazon.com/about-aws/whats-new/2026/04/amazon-bedrock-agentcore-payments-preview/
+ x402가 Polygon을 지원하기 시작했다는 Coinbase 발표: https://www.coinbase.com/developer-platform/discover/launches/x402facilitator-polygon

# 모듈 실패가 아닌 것도 있어염

그러면 지갑 자체는 완전히 안전할까? 또 그것도 아닌 것으로 보입니다. The Block 보도에 따르면 유럽 스테이블코인 발행사 StablR의 EURR과 USDR이 디페그되었습니다. 디페그 되었다는 게 말이 어려워 보이는데 유로 스테이블 코인이 1유로의 가격을 유지하지 못하게 되었고, 달러 스테이블 코인이 1달러의 가격을 유지하지 못하게 되었다는 뜻입니다. 한마디로 닉값 못했다고 보면 됩니다.

StablR의 발행 권한을 3명이 나누어가지고 있었던 것으로 보입니다. 법인카드라고 해볼까요. 법인카드가 하나만 있지 않잖아요. 회사를 위해서 돈을 써야 하는 직책에 있는 사람들은 법인카드를 가지고 있죠. 회사 외부의 어떤 사람이 법인카드를 탈취해서 마구마구 써버린 거랑 비슷한 거 같습니다. 1-of-3 멀티시그 구조라고 하는데요. 3명이 서명할 권한을 갖고, 1명이라도 서명하면 결제가 진행되는 지갑이 있었던 겁니다. 이 지갑에서 스테이블 코인을 발행할 수도 있는 거고요. 공격자는 이 중 한 명의 개인키를 손에 넣었고, 자신을 관리자로 추가하고 기존 소유자들을 교체했다고 합니다. 그리고 새로운 스테이블 코인을 발행한 뒤에 탈중앙화 거래소에 가서 이더리움으로 바꿔버렸습니다. 스테이블 코인을 사줄 돈보다 시장에 쏟아져나오는 스테이블 코인의 양이 많으니까 스테이블 코인의 가격이 떨어져버린 겁니다. 은행 금고를 턴 게 아니라 조폐 권한을 훔쳐서 새 돈을 찍어내고 시장에 던져버린 것이라고도 이해해볼 수 있겠습니다.

보안업체 Blockaid는 이번 사고를 스마트컨트랙트 버그가 아니라 키 관리와 거버넌스 실패로 봤습니다. 사고가 일어난 StablR을 만만하게 본다면 만만의 콩떡입니다. Tether와 Kraken이라는 업계에서 잘 알려진 회사들에게 전략적 투자를 받은 것으로 알려졌고, 유럽 규제환경과 MiCA 규제, 그리고 준비금과 투명성과 같은 단어와 함께 소개되어온 발행사입니다. 이걸 어떻게 해석할 수 있을까요. "암호화폐 업계 완전 허접하고만?"이라고 생각해야 할까요? 아니면 "이게 먼 탈중앙이냐ㅎ;"라고 생각해야 할까요. 

여간 숙제가 많이 남아있는 거 같습니다. 저는 한국의 크립토 그루 오태민 작가님을 좋아합니다. 이 분이 최근에 책을 쓰셨는데요. 신간 <<이더리움 없는 미래는 없다>>의 서문에서 이런 말을 하시더라고요.

> 이더리움은 완벽했기 떄문에 살아남은 것이 아니다. 오히려 실패를 견딜 수 있는 구조였기 때문에 살아남았다. 그 결과 이더리움은 단순한 블록체인 플랫폼을 넘어 새로운 금융 실험이 이루어지는 신대륙이 되었다.
> <<이더리움 없는 미래는 없다>>, 9p

그러니까요. 이런 일들이 다 거름이 된다는 거 아니겠어요? 하여간 바람 잘 날 없는 디파이 생태계 저도 앞으로 잘 쫓아보렵니다! 뭐가 되고 있기는 한 거 같아 분명히!

##### 참고

+ The Block의 StablR EURR·USDR 디페그 보도: https://www.theblock.co/amp/post/402429/stablrs-eurr-and-usdr-depeg-after-attacker-mints-13-5-million-in-unbacked-tokens-through-multisig-exploit
+ CoinDesk의 StablR 토큰 동결 후속 보도: https://www.coindesk.com/markets/2026/05/26/stablr-freezes-usdr-and-eurr-after-attacker-mints-usd13-5-million-in-unbacked-tokens
+ StablR 공식 준비금 증명 페이지: https://www.stablr.com/proof-of-reserve
+ StablR 공식 홈페이지 - EURR·USDR 소개: https://www.stablr.com/
+ StablR USDR 공식 문서: https://docs.stablr.com/docs/what-is-eurr-copy
