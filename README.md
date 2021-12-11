# docker-compose-elastic-kibana
[![Elastic Stack version](https://img.shields.io/badge/Elastic%20Stack-7.15.2-00bfb3?style=flat&logo=elastic-stack)](https://www.elastic.co/blog/category/releases)

도커 컴포저로 엘라스틱서치와 키바나를 띄웁니다.

## 실행 방법

1. demon으로 실행
```
docker-compose up -d
```

2. 로그를 보기 위해 그냥 실행
```
docker-compose up
```

## 종료 하는 방법
docker-compose down

## 디렉토리 마운트

기본 설정대로 하면 엘라스틱서치를 내렸다 올리면 넣어 놓았던 데이터가 모두 날아갑니다.

그래서 아래와 같이 volume부분을 <로컬 디렉토리>:/usr/share/elasticsearch/data 로 해주면 데이터가 로컬에 남아 있습니다.

```
volumes:
      - esdata1:/usr/share/elasticsearch/data
```
를
```
volume:
  - "C:/tmp_elasticsearch:/usr/share/elasticsearch/data"
```
로 바꿔주면 됩니다.

## elastic search안뜰때(78번 에러)

### linux

sudo sysctl -w vm.max_map_count=524288

### windows

wsl -d docker-desktop sysctl -w vm.max_map_count=262144

위 명령어로 max_map_count를 늘립니다.


## Arm에서 안뜰 때
Cpu가 Arm인 경우 아래 에러가 나는 경우가 있습니다.

```
Error: could not find libjava.so  
Error: Could not find Java SE Runtime Environment.
```

아래와 같이 -arm64를 붙여주면 됩니다.
```
image: docker.elastic.co/elasticsearch/elasticsearch:7.14.0-arm64
```

