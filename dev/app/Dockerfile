# 1. 기본 이미지
FROM python:3.14.0-slim

# 2. 작업디렉토리 -> 루트디렉토리가 설정됨
WORKDIR /app

# 3. requirements.txt 복사 및 설치
# . <- 루트 디렉토리를 의미함
COPY requirements.txt .

# 3-1. 실행해라.
RUN pip install --no-cache-dir -r requirements.txt

# 4. 코드복사 -> requirements.txt는 이미 복사되어있음
COPY . .

# 5. 백그라운드(데몬)으로 서비스 가동 -> 컴포즈에서 대체되었음 -> 고로 여기서 안함
# CMD uvicorn . . . . 여기서 커맨드를 지워도 똑같이 작동을 한다?