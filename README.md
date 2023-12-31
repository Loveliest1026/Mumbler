<h1 align="center">
    🗣️ Mumbler 🦻
</h1>

<p align="center">
  <strong>몰래, 은밀하게</strong><br>
  중얼거리기
</p>

<p align="center">
  <a href="*">
    <img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="Mumbler is released under the MIT license." />
  </a>
</p>

## 프로젝트 개요 
1. 프로젝트 소개
: 우리는 컴퓨터 앞에 앉아 공부를 하고, 일을 하면서 수많은 혼잣말들이 머릿 속에 떠올랐다가 사라진다. 어딘가 은밀하게 속삭이고 싶었던 혼잣말들을 긁어모아 오늘 하루동안의 감정 변화와 머릿 속에 스쳐지나갔던 해야 할 일들, 나의 생활 패턴 등을 요약하고 통계내어 리포트로 작성해주는 프로그램을 구상해보았다. 혼잣말을 수집하는 도구로는 크롬 웹 익스텐션을 활용한다. 따로 모바일 기기를 꺼내어 앱을 작동시키거나 프로그램을 실행시켜 화면 전환을 하는 등의 크고 번잡한 행동을 하지 않고 조용히, 은밀하게 어디에도 말 못할 혼잣말을 작성할 수 있도록 하기 위해 크롬 웹 익스텐션을 데이터 수집기로 택하였다. 컴퓨터 앞에 앉아있다면 언제나 켜져있는 크롬창에서 Mumbler 아이콘을 눌러 자그만한 인풋 박스에 몰래 혼잣말을 중얼중얼 작성한다. 이렇게 수집된 혼잣말들은 DB에 저장된다. 이 데이터들을 백엔드 단에서 랭체인을 이용하여 LLM에 입력한다. 작성된 프롬프트에 따라 오늘 하루 동안의 혼잣말들을 분석하고 통계낸 결과를 사용자에게 일일 리포트로 전송한다.
2. 프로젝트 기간
: 2023.11 ~ 2023.12
3. 프로젝트 참여자
: 이재성(백엔드 개발), 신현성(프론트엔드 개발)
4. 사용언어 및 프레임워크
: 파이썬 및 랭체인, 스트림릿

## 사용법

1. Chrome 웹 스토어에서 *Mumbler* 검색
2. 크롬 브라우저에서 Mumbler 익스텐션 아이콘 클릭
3. 혼잣말 입력
4. Collect 클릭
5. Mumbler 아이콘 우클릭 - *옵션* 클릭
6. 다양한 설정 및 혼잣말 수집 결과 확인

## 워크플로우
```
┌──────────────────────────────────────────────────────────────────┐ ┌─────────────────────────────────────────────┐ 
│   ┏━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┓       ┏━━━━━━━━━━━━━━━━━━━━┓ │ │  ┏━━━━━━━━━━━━━━━━━━━┓      ╔═════════════╗ │  (mumbles)    
│   ┃   LLM Framework(Langchain)    ┃  ──▶  ┃  WAS(Spring Boot)  ┃ ──▶  ┃   Web Framework   ┃━━━━━━║   Mumbler   ║ │    Input     ╔═════╗
│   ┗━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┛  ◀︎──  ┗━━━━━━━━━━━━━━━━━━━━┛ ◀︎──  ┃     (Streamlit)   ┃      ║ (Chrome Web ║ ─────────────▶ ║ USR ║ 
│                  │ ▲                                │            │ │  ┗━━━━━━━━━━━━━━━━━━━┛      ║  Extension) ║ ◀︎───────────── ╚═════╝
│                  ▼ │                                │            │ │                             ╚═════════════╝ │    Output
│   ┏━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┓            ╔══════════╗      │ └────────────────── Frontend ─────────────────┘ (daily report)               
│   ┃         LLM(Open AI)          ┃            ║ DB(MySQL)║      │
│   ┗━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┛            ╚══════════╝      │
│                                                                  │
└─────────────────────────── Backend ──────────────────────────────┘       
```

## License

The MIT License.

See [LICENSE](LICENSE)
