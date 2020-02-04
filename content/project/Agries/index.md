---
title: Agries
summary: "클라우드 기반 스마트팜 작물 생장 데이터 분석 시스템<br/>
국회도서관 해커톤 금상 수상"
tags:
- Cloud
- Deep Learning
date: "2019-12-18T00:00:00Z"
weight: 10

# Optional external URL for project (replaces project detail page).
external_link: ""

image:
  caption: Agries 시스템 구성도
  focal_point: Smart

links:
#- icon: twitter
#  icon_pack: fab
#  name: Follow
#  url: https://twitter.com/georgecushen
url_code: ""
url_pdf: ""
url_slides: "files/Agries.pdf"
url_video: ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: ""
---

# 프로젝트 개요
## 수행기간
* 2019.05.10 ~ 2020.01.31 (약 9개월)

## 역할
* 설계 및 개발

# 주요 활동
* 기존 자체 소프트웨어를 통해 열람이 가능했던 환경 데이터를 웹 및 엑셀과 같은 외부 소프트웨어 연계 가능하도록 자동화
* 온실의 수확량 데이터와 환경 데이터를 이용, 딥러닝 분석 기법(LSTM)을 적용해 미래 5일간의 수확량 예측 데이터 제공
* MSA를 적용한 클라우드에 적합한 구조로 쿠버네티스를 활용해 어플리케이션 배포.
* 국산 PaaS인 파스-타를 활용한 웹 프론트엔드 배포

# 성과
* 농장 환경 데이터 웹 및 엑셀을 통한 접근 가능
* 제 2회 국회도서관 해커톤 국회도서관장상(금상) 수상
* 학위 논문 주제 및 제출

# 사용 기술 / 프레임워크
* Flask, Tensorflow, Pandas, Postgresql, OpenAPI, Docker/Kubernetes, Vue.js
