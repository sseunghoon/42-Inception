# 42-Inception

## 요약
***VM과 Docker를 사용하여 가상화 시스템에 대한 이해를 넓힙니다. VM과 Docker의 차이점을 이해합니다.***
<img width="640" alt="image" src="https://github.com/sseunghoon/42-Inception/assets/45088611/66a1ebd1-77bb-4827-b249-b7240bff55e0">

### 기간
2023-09-16 ~ 2023-09-18

## 과제 요구사항 해석
- 전체 프로젝트는 가상머신 안에서 수행되어야 하며, docker-compose를 사용해야 합니다.<br>
  ***💡->Docker 와 VM의 차이점에 대해 아는가?*** (VM으로 가상화를 배웠던 Born2beroot 과제에서 연계)<br>
  ***💡->Multi Container 환경을 구성할 수 있는가?*** 
- 각 서비스는 전용 컨테이너에서 실행되어야 합니다.<br>
  ***💡->이미지 및 컨테이너 생성 방법과 컨테이너 환경 구성에 대해 아는가?***
- 성능 문제를 위해 컨테이너는 Alpine Linux의 두번째 버전 또는 Debian buster에서 빌드해야 합니다.<br>
  ***💡->Base Image에 대해 알고 해당 OS들의 특징을 아는가?***
- 서비스 당 하나의 고유한 Dockerfile을 작성해야 합니다.<br>
  Dockerfile은 Makefile에 의해 docker-compose.yaml에서 호출되어야 합니다.<br>
  즉, 프로젝트의 Docker 이미지를 직접 빌드해야 합니다.<br>
  Dockerhub, 기성품 Docker 이미지를 가져오는 것 등은 금지됩니다. (Alpine/Debian 제외).<br>
  ***💡->Dockerfile을 이용하여 적절한 설정을 직접 작성할 수 있는가?***
### 구성해야 하는 컨테이너 및 네트워크+볼륨
- TLSv1.2 또는 TLSv1.3만 포함된 Nginx를 구성하는 컨테이너
- Nginx 없이 Wordpress + php-fpm(설치 및 구성해야 됨)을 구성하는 컨테이너
- Nginx 없이 MariaDB만 포함하는 컨테이너
- Wordpress 데이터베이스가 포함된 볼륨
- Wordpress 웹 사이트 파일이 포함된 두 번째 볼륨
- 컨테이너 간의 연결을 설정하는 도커 네트워크
- crash가 발생할 경우 재시작 해야 합니다.

## 아키텍처
<img width="742" alt="image" src="https://github.com/sseunghoon/42_Inception-Infra/assets/45088611/3f079604-ac0f-4d99-bc0c-e9f54b1338dc">

## Directory Structure
<img width="509" alt="image" src="https://github.com/sseunghoon/42_Inception-Infra/assets/45088611/9271817c-ab60-4df1-96c6-f3e9b45a9d31">



