# docker

로컬서버의 경우 docker 데스크톱으로 대체한다.

## 개발서버

sudo apt-get update

- apt 가 https 에서 리포지토리를 사용할 수 있게 처리
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings

- 공식 GPG 키 추가
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

echo \
"deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
$(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}") stable" | \
sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update

- 도커설치
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

- 도커 테스트
systemctl status docker

- 사용자 모드 설정
sudo usermod -aG dockeer $USER

도커 명령어
- docker version : 버전을 확인
- docker image : 이미지 관련 처리
  + ls
  + pull [nginx...]

## 참조자료
 <https://docs.docker.com/engine/install/ubuntu/>
