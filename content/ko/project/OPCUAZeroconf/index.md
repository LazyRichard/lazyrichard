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
## 프로젝트 배경
* 공장에서 사용하는 다양한 장치를 서버와 연결하여 실 사용 환경을 구축할 때, 스마트 기기에 능숙하지 않은 작업자는 어려워 하는 점에 착안해 OPC-UA 서버의 인포메이션 모델을 활용하여 장치와 서버간 제로 구성(Zero configuration) 시스템 개발

## 수행기간
* 2017.11.02 ~ 2017.12.07 (약 1개월)

## 역할
* 설계 및 개발

# 주요 활동
* OPC-UA의 파이썬 구현체를 사용하여 라즈베리파이 기반 서버 구현
* mDNS와 mDNS-SD를 활용해 다양한 종류의 장치를 네트워크 내에서 검색
* 각 센서에서 지원하는 기능들을 XML형태의 Information Model로 기술하여 저장 하여 연결 시점에 서버로 전송함으로써 장치를 사용하기 위한 추가적인 설정 불필요
* 장치를 검색하고 연결하는 UI를 Node-RED를 이용해 제작하여 사용자는 드롭다운 메뉴로 검색된 장치를 확인할 수 있고 버튼 몇 번으로 장치 등록 가능

# 성과
* 2019 스마트공장 • 자동화산업전 스마트공장 운영설계 전문인력 양성사업 우수 프로젝트 발표

# 사용 기술 / 프레임워크
* Node-RED(javascript), OPC-UA(Python), Arduino(C++), mDNS, mDNS-SD
