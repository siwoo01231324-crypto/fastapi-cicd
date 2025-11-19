# ADD(파일/디렉토리 추가), COPY(파일 복사) 명령
# 이미지가 생성될 때 컨테이너가 추가될 때, 파일, 디렉토리를 추가하는 기술
# 제외하고 싶은 파일이 있다면 -> .dockerignore
# ADD : 특정경로, URL상에 존재하는 파일/디렉토리 원하는 위치에 저장, 추가
#       URL은 다운로드 해서 진행, 압축파일은 압축 해제해서 저장
# COPY : 파일만 카피.파일명 변경 가능
FROM ubuntu 

# 압축 파일을 컨테이너로 ADD 
ADD web.tar /home/

# url 다운로드 후 추가
ADD https://raw.githubusercontent.com/ultralytics/yolov5/master/requirements.txt /home/requirements.txt
 
# 파일 추가
ADD readme.md /home/readme2.MD

# 특정 파일 추가 (패턴 적용) -> /dockerignore에 의해서 무시됨
ADD po*.txt /home/

# 특정 패턴 추가
# ? = 문자 1개만 들어감 -> t1.txt만 추가됨
ADD t?.txt /home/

# WORKDIR 지정
WORKDIR /usr/app
# 현재 위치에 모든 내용을 작업 디렉토리로 복사 -> 소스코드 복사할때 활용
COPY . .