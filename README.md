# docker-compose-elastic-kibana
도커 컴포저로 엘라스틱서치와 키바나를 띄웁니다.

## 실행 방법
docker-compose up -d

## 종료 하는 방법
docker-compose down

## elastic search안뜰때(78번 에러)
sudo sysctl -w vm.max_map_count=524288
위 명령어로 max_map_count를 늘린다.
