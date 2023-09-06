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

## 프로젝트 개요
### 프로젝트 배경
* 국책과제 "과채류 재배에 최적화된 하이브리드 보광등 개발"을 수행하던 중, 생산량 개선 등의 효과 분석 방안 논의 도중 온실에서 사용중인 환경 제어 시스템과 작물 생장 데이터 수집 프로세스가 너무 복잡한 것을 발견하여 이를 개선하고자 기획

### 프로젝트 목표
* 자체 소프트웨어를 통해서만 열람이 가능했던 환경 데이터를 서버 기술과 자동화를 통해 웹 및 엑셀과 같은 외부 소프트웨어와 연계 가능하도록 제작하여 환경 데이터의 접근성 향상
* 온실에서 측정하는 생육 데이터의 효과적인 관리를 위한 관리 시스템 및 환경 데이터와 연계하여 미래 수확량 예측 기능을 제공

### 수행기간
* 2019.05.10 ~ 2020.01.31 (약 9개월)

### 역할
* 설계 및 개발

## 주요 활동
* Python Flask 기반 백엔드 및 Vue.js 기반 프론트 엔드로 구성하고 Postgresql를 데이터베이스로 사용
* 자체 환경 제어 솔루션에서 사용하는 CSV파일을 Redis MQ기반 Worker를 이용해 파싱하여 REST API를 통한 JSON 형태로 제공. 엑셀 및 PowerBI와 같은 다양한 소프트웨어를 통해 환경 데이터 실시간 접근 가능
* SPA 웹 프론트엔드 라이브러리로 반응형 프론트 엔드 제작
* 딥러닝 알고리즘(LSTM)을 적용해 온실의 수확량 데이터와 환경 데이터를 이용하여 미래 5일간의 수확량 예측 데이터 제공
* Gitlab을 이용한 형상 관리 및 Docker 이미지 제작으로 클라우드에 적합한 구조.
* 쿠버네티스로 서버, DB, Redis, Worker 어플리케이션을 배포하였고 국산 PaaS인 파스-타를 활용해 웹 프론트엔드 배포
Open-API 및 Open-API Generator을 활용한 개발 프로세스 적용으로 개발 기간 단축

## 성과
* 농장 환경 데이터 웹 및 엑셀을 통한 접근 가능
* 제 2회 국회도서관 해커톤 국회도서관장상(금상) 수상
* "클라우드 기반 스마트팜 작물 생장 데이터 분석 시스템 설계 및 구현" 석사 학위 논문

## 사용 기술 / 프레임워크
* Flask, Tensorflow, Pandas, Postgresql, OpenAPI, Docker/Kubernetes, Vue.js
