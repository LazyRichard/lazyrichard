---
title: 서버/클라이언트 기반 채팅 및 P2P 파일 공유 시스템
summary: "서버/클라이언트 기반 그룹 채팅 및 P2P 파일 공유 시스템<br/>
리눅스 epoll을 사용한 IO 다중화 서버 모델 채용으로 싱글 쓰레드로 기능 구현"
tags:
- Term Project
- Other
date: "2019-12-18T00:00:00Z"
weight: 60

# Optional external URL for project (replaces project detail page).
external_link: ""

image:
  caption: 시스템 구성도
  focal_point: Smart

links:
#- icon: twitter
#  icon_pack: fab
#  name: Follow
#  url: https://twitter.com/georgecushen
url_code: "https://bitbucket.org/JunminSeo/kpu_eos_termproject"
url_pdf: "files/P2P-Project-Reports.pdf"
url_slides: ""
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
* 2016.10.11 ~ 2016.12.19 (약 2개월)

## 역할
* 팀장
* 설계 및 개발

# 주요 활동
* Epoll을 활용한 싱글 쓰레드 기반 채팅 및 P2P 파일 공유 서버로 다중 클라이언트 지원 가능
* 추가적인 기능 추가가 용이하도록 서버/클라이언트 간 유연한 프로토콜 설계

# 성과
* 해당 수업 텀프로젝트 만점으로 A+ 성적

# 사용 기술 / 프레임워크
* C, Multi-thread, epoll