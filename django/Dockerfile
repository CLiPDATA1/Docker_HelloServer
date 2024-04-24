#############
# 도커 과정 #
#########################################################
# 0. 사전 작업                                          #
# pip freeze > requiremtens.txt                      #
# 도커 파일과 같은 위치에 생성해둘것                     #
# 도커 파일의 위치는 manage.py의 위치에 둘 것            #
# ※ 경로는 상관없음                                     #
# (단 경로 찾기를 수행해야 하기 때문에 옆에 두라고 한것)  #
##########################################################



# Python 3.11 환경을 사용
FROM python:3.11

# PYTHONDONTWRITEBYTECODE: .pyc 파일을 생성하지 않도록 설정합니다. .pyc 파일은 파이썬 소스 코드를 컴파일한 결과
# PYTHONUNBUFFERED: 파이썬이 표준 출력(stdout)과 표준 오류(stderr)의 버퍼링을 비활성화
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

# 작업 공간 /usr/scc/app
WORKDIR /usr/sec/app

# /usr/scc/app에 Dockerfile 있는 위치의 내용들을 복사해서 올린다.
COPY . .

# image가 올라 갈 시 실행 되는 명령어
# Ubuntu 환경에 명령어 처리를 수행
RUN apt update && \
    apt upgrade -y

# Upgrade pip3
RUN pip3 install --upgrade pip

# requiremtens.txt의 패키지들을 image
RUN pip3 install -r requiremtens.txt

###### 싱글 서버 열때 아래의 구문은 주석 해도 됨
# EXPOSE 8000

# CMD ["python", "./manage.py", "runserver", "0.0.0.0:8000"]


##################
# CMD 명령어 실행#
##################
# ALLOWED_HOSTS = ['*'] 서비스 허용 필요
# 0.0.0.0:8000 서버를 열때 필요



######################### 서버 실행 ####################################
# docker run --name hello_django -itd -p 8000:8000 hello_django_server #
########################################################################