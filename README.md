# Scoring-Site

### 도커 기반으로 구동하는 오픈소스 (ver.ubuntu 20.04)

1. 원하는 위치에 폴더를 새로 생성 후 해당 폴더로 이동하기. 
- `mkdir Qingdao`
- `cd Qingdao`
2. openApi Url 주소 clone 한 후 생성된 OnlineJudgeDeploy 폴더로 이동.
- `git clone https://github.com/QingdaoU/OnlineJudgeDeploy.git`
- `cd OnlineJudgeDeploy`
3. docker-compose를 사용하기 
- `docker-compose up -d`
- 여기서 docker 관련 문제가 발생할 경우에는 docker와 docker-compose를 먼저 설치 후에 시도하기
4. docker-machine 리스트 확인하기 
- `docker-machine ls`
5. docker-machine 리스트에서 default가 없으면 default를 생성해준다.
- `docker-machine create default` or `default-machine create --driver virtualbox default`
6. default 도커 머신을 생성시 ip 관련해서 제대로 생성이 되지 않을 경우 다음의 코드 실행
- `VBoxManage natnetwork list`로 natnetwork 리스트 확인 
- `VBoxManage natnetwork stop --netname '실행 중인 NatNetwork 이름'`
- `VBoxManage natnetwork start --netname '실행 시킬 NatNetwork 이름'`
7. 현재 실행 중인 도커 의 ip 확인 
- `docker-machine ip`
8. 현재 실행 중인 전체 컨테이너 리스트 출력
- `docker ps -a`
