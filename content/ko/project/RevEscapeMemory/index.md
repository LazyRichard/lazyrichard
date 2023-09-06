---
title: 리버스 방탈출 소녀의 기억 장치
summary: "아두이노 기반 센서에 PySide2(PyQT5)와 aync http framework를 활용한 MSA 기반 방탈출용 장치 설계 및 제작.<br/>
리버스 방탈출 웹 모니터링 가능 장치 납품"
tags:
- IoT
date: "2019-08-01T00:00:00Z"
weight: 30

# Optional external URL for project (replaces project detail page).
external_link: ""

image:
  caption: 설치된 장치
  focal_point: Smart

links:
#- name: 리버스 방탈출 바로가기
#  url: https://www.reverseescape.com/
url_code: ""
url_pdf: ""
url_slides: ""
url_video: ""

---

## 프로젝트 개요
### 프로젝트 배경
* 리버스 방탈출 아기돼지 삼형제 후속 프로젝트로 총 9개 RFID 태그를 활용해 적합한 사진을 출력하는 시스템 개발
### 프로젝트 목표
* 라즈베리파이 및 태그 인식 센서를 활용해 특정 RFID 태그가 감지되면 적합한 사진을 출력하는 시스템 제작
* 원격에서도 손 쉽게 시스템의 상태와 제어를 할 수 있는 웹 기반 콘솔 기능이 포함된 장치 제작

### 수행기간
* 2019.05.02 ~ 2019.07.31 (약 3개월)

### 역할
* 설계 및 개발

## 주요 활동
* 라즈베리파이에 Python Async 웹 프레임워크인 Sanic을 사용해서 서버 설계. 센서 데이터는 ZeroMQ를 활용해 서버와 통신 가능한 구조로 설계
* Vue.js 기반 웹 콘솔과 QT5기반 GUI는 REST-API를 통해 서버와 통신. 모든 이벤트는 Server Sent Event를 활용해 시스템 상태 변동을 이벤트 기반 제어가능하도록 설계
* 3D 모델링 및 프린팅을 활용한 맞춤형 장치 디자인

## 성과
* 웹 콘솔을 통한 장치 모니터링 및 제어 가능

## 사용 기술 / 프레임워크
* Sanic(Python), PySide2(PyQT5), Vue.js(javascript), Arduino(C++), Solidworks, 3D Printing
