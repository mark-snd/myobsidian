---
tags: [coding, dev, AI, trading, LLM, multi-agent]
---

# QuantAgent

출처: https://github.com/y-research-sbu/QuantAgent

멀티 에이전트 기반 주식 트레이딩 분석 시스템. LangChain + LangGraph로 구현된 4개의 전문 에이전트가 협력해 매매 신호를 생성.

---

## 에이전트 구성

1. Indicator Agent — RSI, MACD, Stochastic Oscillator 등 기술적 지표 계산
2. Pattern Agent — 차트 패턴 인식 및 매칭
3. Trend Agent — 추세 채널 분석, 지지/저항 구간 파악
4. Decision Agent — 위 3개 에이전트 결과 종합 → 진입/청산 신호 생성

## 기술 스택

- LangChain, LangGraph
- LLM: OpenAI GPT-4, Anthropic Claude, Qwen, MiniMax
- 데이터: Yahoo Finance (yfinance)
- 기술적 분석: TA-Lib
- 백엔드: Flask
- Python 3.11

## 출처

- 논문: arXiv 2509.09995
- 소속: Stony Brook Univ, CMU, UBC, Yale, Fudan Univ
- 라이선스: MIT
