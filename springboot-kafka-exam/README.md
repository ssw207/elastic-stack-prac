# 카프카 연동 예제 
## 실행방법
1. 카프카 docker 실행
2. boot 서버 실행
3. `src > test > http >prod.http` 파일을 실행해 exam 토픽에 데이터 전송
4. `http://localhost:9001/topic/exam/messages?partition=0&offset=0&count=100&keyFormat=DEFAULT&format=DEFAULT` 접속해 토픽확인 