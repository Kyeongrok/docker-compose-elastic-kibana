# docker-compose-elastic-kibana
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

## elastic search안뜰때(78번 에러)

### linux

sudo sysctl -w vm.max_map_count=524288

### windows

wsl -d docker-desktop sysctl -w vm.max_map_count=262144

위 명령어로 max_map_count를 늘립니다.
