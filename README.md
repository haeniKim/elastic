# Elastic Stack
> 참고 : https://esbook.kimjmin.net/
## Beats
> single purpose data shippers
## Logstash
> a server side data processing pipeline

### 데이터 처리를 위한 과정
`Inputs` -> `Fileters` -> `Outputs`
* 입력 : 다양한 데이터 저장소로부터 데이터 입력 받음
* 필터 : 데이터 확장, 변경, 필터링 및 삭제
* 출력 : 다양한 데이터 저장소로 데이터 전송

## Elasticsearch
> search and analytics engine for all types of data
* node : an instance of Elasticsearch
* cluster : a collection of Elasticsearch nodes
* document is a serialized JSON object

### 특징
**Open Source**

**Real-Time**
* 하둡 시스템과 달리 클러스터가 실행되고 있는 동안 계속해서 데이터가 입력되고, 실시간에 가까운 속도로 색인된 데이터의 검색, 집계 가능

**Full Text**  
* inverted file index 

**REST API** 
* 모든 데이터 조회, 입력, 삭제를 http 프로토콜을 통해 Rest API로 처리

**Multitenancy**
* 서로 다른 인덱스들을 별도의 커넥션 없이 하나의 질의로 묶어서 검색, 검색 결과들을 하나의 출력으로 도출

- 프로그램과 인스턴스의 차이
    - 인스턴스 : 프로그램 실행시 메모리에 올라가 있는 상태. 실행되고 있는 것. 서비스가 되고 있는 상태
- **node** : instance of ES (실행중인 상태)
    - 데이터 저장, 제어, 수집 처리 등 node들은 역할에 따라 나누고 합할 수 있음.
- **cluster** : collection of ES nodes
- **document** : a serialized JSON object
- 설치 환경
    - on-premises : 물리적인 하드웨어에 설치
    - cloud : 가상화 환경 위에 설치(ex. kubernetes)
    - hybrid : 하나는 cloud, 하나는 on premises

### DSL
#### GET

- `GET /`  : request to ES returns basic details about the cluster
- `GET _cat/indices` : displays the current indexes in the cluster
- `GET {dataset}/_search` : "match all" query that returns 10 documents in an index


## Kibana
> frontend application, search ans data visualization capabilities for data indexed in Elasticsearch

### 주요 기능
**Discover**
* Elasticsearch에 색인된 소스 데이터 검색

**Visualize**
* aggregation 집계 기능을 통해 조회된 데이의 통계를 다양한 차트로 표현할 수 있는 패널을 만드는 메뉴, 패널 조합을 통해 대시보드를 만들 수 있음.

**Dashboard**
*  Visualize 메뉴에서 만들어진 시각화 도구들을 조합해서 대시보드 화면을 만들고 저장, 불러오기 등을 할 수 있는 메뉴

## Observability
### Metricbeat

> **Collects metrics from the operating system and from
services running on the server**
>
