# RUN : shell 방식으로 기술
# /bin/bash 환경에서 실행됨
# 표현 예시 
# RUN echo "메세지" <- 이 방식으로 주로 구성
# RUN ["echo",  "메세지"]
# RUN ["/bin/bash", "-C", "echo":"메세지"]

# CMD
# 데몬 실행 -> 백그라운드에서 가동
# 컨테이너 내부에서만 명령어 작동
# 도커 파일 내부에서 오직 1회만 기술 가능
# 만약, 여러개 있다면 -> 마지막 것만 유효함
# EXEC 스타일
# CMD ["python" , "app.py"]
# shell 스타일
# CMD python app.py

# EXPOSE
# 컨테이너가 사용할 포트

# 베이스 이미지 구성
FROM ubuntu 

# 베이스 관리 패키지 목록 최신으로 업데이트
RUN apt-get -y update && apt-get -y upgrade

# nginx 설치
RUN apt-get -y install nginx

# 웹서버
EXPOSE 80

# html 추가
# default.conf 수정하여 프록시 설정 <- 추가 가능



# 백그라운드 가동
# 컨테이너 생성된 후 작동되는 데몬 서비스
CMD [ "nginx","-g","daemon off;" ]

# 이미지 생성 -> 컨테이너 생성 -> 접속 테스트 (실습)
# 이미지 생성
# docker build -t test_ubuntu:1.3 ./step3
# 확인
# docker image ls
# 컨테이너 생성
# docker run -itd -p 80:80 --name my_nginx2 test_ubuntu:1.3
# 접속
# 