# 호스트 os와 컨테이너간 폴더간 볼륨설정
# nginx 경우 -> 설정파일이 공유되면 수정부분을 호스트os에서 간편하게 진행 가능함.
FROM nginx 

# ["호스트OS상 특정 경로 지정","컨테이너상 특정 경로"]
VOLUME ["/config","/etc/nginx/conf.d"]