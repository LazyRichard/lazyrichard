---
title: 리버스 방탈출 아기돼지 삼형제 장치
summary: "아두이노 기반 센서와 PySide2(PyQT5)를 활용한 방탈출용 장치 설계 및 제작<br/>
리버스 방탈출 장치 납품"
tags:
- Other
date: "2019-03-01T00:00:00Z"
weight: 40

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
* 기존 업체에서 사용하던 시스템이 PC Unity 기반이라 장비 가격이 높고, 브레드보드를 이용한 임베디드 장치 설계로 잦은 오작동과 유지보수가 어려운 문제점 발생.
* 라즈베리파이를 기반으로한 제어 컨트롤러 채용으로 재료비 절감 효과 및 자체 설계한 PCB를 이용한 센서로 높은 안정성을 통해 문제를 해결하고자 프로젝트 제안

### 프로젝트 목표
* 특정 RFID 태그가 감지되면 적합한 영상을 출력하는 시스템 개발

### 수행기간
* 2019.02.26 ~ 2019.03.28 (약 1개월)

### 역할
* 설계 및 개발

## 주요 활동
* 라즈베리파이에 QT5기반 GUI 프로그램을 통해 영상을 출력하는 시스템 제작. 외부 센서 데이터는 Multi-Thread 기반 수집 프로그램과 자체 설계한 프로토콜을 사용해 송수신
* 자체 제작한 PCB를 활용한 센서 모듈을 통해 안정적인 태그 인식 및 통신
* 3D 모델링 및 프린팅을 활용한 맞춤형 기구 장치 디자인

## 성과
* PC가 아닌 임베디드 장비를 활용한 장치 개발로 재료비 50% 이상 감소

## 사용 기술 / 프레임워크
* PySide2(PyQT5), Arduino(C++), Solidworks, 3D Printing
