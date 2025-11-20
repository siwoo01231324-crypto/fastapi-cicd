# 구조

# 루트
. 
L app
    L Dockerfile            : fastapi 관련 도커파일 (핵심 서비스)
    L main.py               : 파이썬 구성된 fastapi 기반 코드(개발할 내용)
    L requirements.txt      : 서비스 구동을 위한 필요 패키지 목록
L nginx                     
    L nginx.conf            : nginx에서 fastapi로 프록시 하는 구성 (설정파일)
L docker-compose.yml        : 컴포즈 파일 -> n개의 컨테이너 구성->연결->구동

# 구성 명령
## 생성 및 실행
docker-compose up -d --build
## 종료 및 제거
docker-compose down

# 시크릿 변수
MYSQL_ROOT_PASSWORD
MYSQL_USER
MYSQL_PASSWORD
DOCKER_USERNAME
DOCKER_PASSWORD
EC2_HOST
EC2_USERNAME
EC2_KEY

# 흐름도 -> Docker 기반 cicd를 위한 
로컬 pc 개발 -> git 특정 브런치 push -> 이벤트 감지 -> git action 작동
-> xxx.yml에 상세하게 jobs들이 기술 -> 커스텀으로 구성
-> 소스코드 체크아웃 (git action에서 제공하는 리눅스에 소스코드 체크아웃) -> 
-> 검증
-> 도커 허브 로그인 -> git action에서 제공하는 리눅스에 세션이 생성됨(사용자명,엑세스토큰 제공 {시크릿 변수로})
-> fastapi 앱, nginx 이미지(커스텀된), 이미지를 생성(build), dockerfile을 이용하여 
-> push (본인 계정의 도커허브 레퍼지토리) -> 여기 올라가야 아마존에서 pull 해오지