# ES
## 실행
1. .env docker-compse.yml 파일을 같은 폴더에 둔다.
2. `docker-compose up -d`을 입력해 도커를 실행한다.
   - docker 실행시 .env에서 관련 설정정보를 읽어 실행한다.
   - 기본적으로 node 3개와 키바나가 실행된다.
3. localhost:9200으로 키바나에 접속한다.
   - .env 파일에 사전에 입력해놓은 ES 아이디와 비밀번호를 입력한다.
   - 아이디 : elastic, 비밀번호 : adminadmin 입력

# 키바나
## 플러그인설치
-  Integrations 메뉴에서 플러그인을 선택해 설치 

# 이슈사항
## ELK
- `ERROR: for kibana  Container "a442792461fd" is unhealthy.`
  `ERROR: Encountered errors while bringing up the project.`
  - docker es 컨테이너 확인 es컨테이너가 뜨지 않아 키바나 컨테이너 구동실패시 오류발생 
- `error: [1] bootstrap checks failed [1]: max virtual memory areas vm.max_map_count [65530] is too low, increase to at least [262144] 에러 발생시`
  - 파워쉘에서 아래 명령어 입력
     ```shell
     wsl -d docker-desktop
     sysctl -w vm.max_map_count=262144
     ```
## 로그스태시 
`ERROR: for logstash  Cannot start service logstash: OCI runtime create failed: container_linux.go:380: starting container process caused: process_linux.go:5
45: container init caused: rootfs_linux.go:76: mounting "/run/desktop/mnt/host/c/WorkSpaceITL/elastic-stack-prac/docker/elk/examples/logstash.conf" to rootf
s at "/usr/share/logstash/pipeline/logstash.conf" caused: mount through procfd: not a directory: unknown: Are you trying to mount a directory onto a file (o
r vice-versa)? Check if the specified host path exists and is the expected type
`

# 참고
공식문서 : https://www.elastic.co/guide/en/elasticsearch/reference/8.2/docker.html