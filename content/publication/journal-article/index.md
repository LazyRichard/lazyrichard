---
title: "클라우드 기반 스마트팜 작물 생장 데이터 분석 시스템 설계 및 구현"
authors:
- admin
date: "2019-12-01T00:00:00Z"
doi: ""

# Schedule page publish date (NOT publication's date).
publishDate: "2020-01-27T00:00:00Z"

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["7"]

# Publication name and optional abbreviated publication name.
publication: "한국산업기술대학교 일반대학원"
publication_short: ""

abstract: "국내 농업은 농가 감소, 고령화 등의 문제로 농업의 성장, 소득, 수출이 정체되고 있어 많은 어려움이 있다. 이를 극복하기 위한 방안으로 농업에 4차 산업혁명의 중요한 흐름 중 하나인 정보 통신 기술을 접목한 스마트 팜 적용의 중요성이 커지고 있다. 하지만 현재의 농작물 관리 시스템은 대부분 온실 내부 환경 모니터링과 원격 제어 기능에 초점을 맞추고 있어 생육 데이터 수집을 통한 생산량 예측 등의 과학적 활용이 미비하다. 본 논문은 이러한 문제들을 해결하기 위해 생육 데이터를 수집하고, 수집된 데이터와 환경 데이터를 이용해 수확량을 예측하는 시스템을 제안하였다. 본 논문에서 제안하는 시스템은 딥러닝 기법을 통한 인공지능 기반의 예측 수확량을 제공하여 맞춤형 작물 생장 관리가 가능하다. 이에 따라 경쟁력 있는 작물 관리 정책 수립 데이터에 기반한 의사결정이 가능할 것으로 기대된다.
작물의 다양한 특성을 저장하고 이를 활용하기 위해서는 유연한 데이터 구조가 필요하다. 이를 위해 JSON을 이용한 데이터 구조를 활용하는 방식이 연구되었으나, 기존 방법은 데이터 구조를 기술하는 스키마가 표준화되어 있지 않아 데이터의 상호 운용성 확보가 어려워 다양한 시스템에 적용할 수 없는 문제가 있다. 본 논문에서 제안한 시스템은 JSON 스키마를 활용해 표준화된 방법으로 데이터 구조를 기술하여 입력 데이터의 유효성을 검증한다. 따라서 다른 시스템에서도 동일한 구조를 활용할 수 있어 확장성이 우수하고 스키마를 효율적으로 관리할 수 있다.
국내의 온실은 외국에 비해 상대적으로 소규모로 각각의 농가에서 IT 기반 시설의 설치와 유지는 인원 및 비용과 같은 현실적 이유로 인해 어려운 실정이다. 따라서 본 논문에서는 마이크로서비스 아키텍처를 적용한 클라우드 기반 시스템을 제안하였으며, 이를 통해 IT 기반 시설 관리 요소를 배제할 수 있어 소규모 농가에서도 비교적 쉽게 도입이 가능한 장점이 있다.
마이크로서비스 아키텍처는 개별 서비스들이 서로 느슨하게 연결되어 있어 모놀리스 아키텍처보다 유연한 구조를 가질 수 있지만 동일한 기능을 위해 더 많은 구성 요소가 필요하다. 이는 개별 서비스의 API 통일이 어렵고 코드 중복 문제가 발생하여 개발과 관리 모두 불편함을 야기한다. 본 논문에서 제안하는 시스템은 Open-API 명세서를 활용하여 전체 서비스의 API를 관리하는 방법론을 적용하였다. 따라서 기존 시스템에 비해 높은 API 관리 복잡도와 파편화 문제를 해결하였다. 추가로 Open-API Generator를 활용하여 클라이언트 라이브러리를 자동 생성하는 방법을 통해 기존의 단점이었던 개별 서비스 간 코드 중복 문제를 해결하고 개발 기간을 단축할 수 있었다.
또한 본 논문에서 제안한 시스템을 검증하기 위해 약 20,000㎡ 규모 온실에 테스트 베드를 마련하고 데이터 수집과 시험 과정을 통해 시스템의 정상 작동 여부와 수집된 데이터 분석을 통한 수확량 예측이 가능함을 확인하였다.
 본 논문에서 제안하는 클라우드 기반 작물 생육 데이터 수집·분석 시스템은 클라우드 환경에 적합한 아키텍처를 적용하여 개발 및 유지보수가 쉽고, 유연한 데이터 구조로 다양한 생육 데이터를 손쉽게 저장 및 관리가 가능하다. 또한 딥러닝 기법을 적용한 수확량 예측 기능은 농업인에게 경영 지표와 설정된 환경 제어 값을 검증할 수 있는 기반을 제공한다. 이를 통해 향후 4차 산업혁명과 인공지능 시대에 맞는 최적화된 농작물 관리 인프라 구현이 가능하며, 기존의 국내 농가들의 경쟁력 향상에 기여할 수 있을 것으로 기대한다."

# Summary. An optional shortened abstract.
#summary: Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis posuere tellus ac convallis placerat. Proin tincidunt magna sed ex sollicitudin condimentum.

tags:
- Cloud
- Deep Learning
featured: true

# links:
# - name: ""
#   url: ""
url_pdf: ""
url_code: ''
url_dataset: ''
url_poster: ''
url_project: ''
url_slides: ''
url_source: ''
url_video: ''

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
image:
  caption: 'Image credit: [**Unsplash**](https://unsplash.com/photos/jdD8gXaTZsc)'
  focal_point: ""
  preview_only: false

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
projects:
- Agries

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
slides: ""
---
