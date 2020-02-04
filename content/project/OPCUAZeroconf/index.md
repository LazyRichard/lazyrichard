---
title: OPC-UA 서버-장치간 자동 연결 시스템
summary: "OPC-UA 서버와 다양한 통신 방식을 갖는 장치간 자동 검색 및 연결(Zeroconf) 구현<br/>
스마트공장 운영설계 전문인력 양성사업 우수 프로젝트 발표"
tags:
- IoT
- OPC-UA
- Term Project
date: "2017-10-01T00:00:00Z"
weight: 20

# Optional external URL for project (replaces project detail page).
external_link: ""

image:
  caption: 구현된 시스템
  focal_point: Smart

links:
url_code: ""
url_pdf: ""
url_slides: "files/OPC-UA-Zeroconf.pdf"
url_video: ""

---

# 프로젝트 개요
## 수행기간
- 2017.11.02 ~ 2017.12.07 (약 1개월)

## 역할
- 설계 및 개발

# 주요 활동
- 다양한 종류의 장치를 OPC-UA 서버에 연결하기 위해 필요한 복잡한 절차를 자동화
사용자는 장치에 전원을 공급하면 OPC-UA에서 장치를 자동으로 검색해 연결 가능
- 장치에서 제공하는 기능들을 OPC-UA 인포메이션 모델로 기술하여 연결 시점에 서버로 전송함으로써 장치를 사용하기 위한 추가적인 설정 불필요


# 성과
- 2019 스마트공장 • 자동화산업전 스마트공장 운영설계 전문인력 양성사업 우수 프로젝트 발표

# 사용 기술 / 프레임워크
- Node-RED(javascript), OPC-UA(Python), Arduino(C++), mDNS, mDNS-SD
