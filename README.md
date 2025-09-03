# 📊 Django Fintech Portfolio
> **주식·부동산 등 다양한 자산을 포트폴리오로 관리하고,  
투자 전략과 매매 일지를 기록·토론·공유할 수 있는 플랫폼**

---

## 🚀 프로젝트 개요
이 프로젝트는 **Django**를 활용해 **금융 포트폴리오 관리 + 전략 공유 + 투자 일지 기능**을 제공하는 웹 애플리케이션입니다.  
사용자는 자신의 자산을 포트폴리오로 등록하고, 투자 전략을 카드 형태로 작성하여 **공유/토론**할 수 있습니다.

---

## 📅 개발 일정
| 주차 | 기간 | 목표 |
|------|--------|----------------|
| **Week 1** | 9/3 ~ 9/6 | 기획 및 설계, 환경 세팅 |
| **Week 2** | 9/9 ~ 9/13 | 핵심 기능 개발 및 통합 |
| **Week 3** | 9/16 ~ 9/18 | 테스트, 배포, 발표 준비 |

---

## 🛠️ 기술 스택
| 영역 | 사용 기술 |
|------|-----------|
| **Frontend** | HTML5, CSS3, JavaScript, Bootstrap 5 |
| **Backend** | Django 5.x |
| **Database** | PostgreSQL (운영), SQLite (개발) |
| **시세/환율 연동** | FinanceDataReader, yfinance |
| **차트 시각화** | Chart.js, Plotly |
| **협업** | GitHub, Notion, Discord |
| **배포** | Render / PythonAnywhere |

---

## ✨ 핵심 기능 (MVP)
### **① 포트폴리오 통합 관리**
- 주식·ETF·부동산 등 다양한 자산을 등록하고 통합 관리
- 실시간 시세 및 환율 연동 → 평가금액, 수익률 자동 계산
- 자산 비중 및 손익 추세를 **차트로 시각화**

### **② 투자 전략 & 매매 일지**
- 거래 시 매매 이유를 기록 → 자동으로 매매 일지 생성
- 투자 전략을 카드 형태로 작성해 관리
- 전략 카드별 성과 분석 기능 제공

### **③ 전략 공유 & 토론 (SNS 기능)**
- 전략 카드 및 포트폴리오를 **선택적으로 공유**
- 공개 범위 설정 가능 (전체 / 초대 기반 / 나만 보기)
- 댓글, 좋아요, 해시태그 기능을 통한 전략 토론

---

## 🧩 시스템 아키텍처
```mermaid
graph TD
    User[사용자] -->|로그인/회원가입| Auth[Django Auth]
    User -->|포트폴리오 CRUD| PortfolioDB[(Portfolio DB)]
    User -->|전략 카드 작성| StrategyFeed[(Strategy Feed)]
    StrategyFeed --> Comment[(댓글)]
    MarketAPI[시세/환율 API] --> PortfolioDB
    PortfolioDB --> Dashboard[대시보드]
    Dashboard --> ChartJS[차트 시각화]
