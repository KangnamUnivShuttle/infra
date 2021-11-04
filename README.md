# infra

## 30주년 행사 축제 웹 페이지 작업 안내

<div align="center">
    <img width="475" alt="스크린샷 2021-11-04 오후 1 19 00" src="https://user-images.githubusercontent.com/16532326/140257369-cae41a88-4bbd-4dd2-b769-aa9365683509.png">
</div>

계정 festival 를 이용하여 접속 후 `web` 디렉토리에 웹페이지 파일을 저장

https://kws1.kangnam.ac.kr/festival 에서 작업 결과 확인 가능

FTP를 지원하지 않으므로 파일 전송시 `scp` 명령어를 사용하거나 Github 를 이용하여 `git clone` 하여 사용하는 방법을 이용하기 바람

## Live server info

Ubuntu 14.04 LTS

Docker install progress

```
sudo apt-get install linux-image-extra-$(uname -r) linux-image-extra-virtual
wget https://download.docker.com/linux/ubuntu/dists/trusty/pool/stable/amd64/docker-ce_18.06.1~ce~3-0~ubuntu_amd64.deb
sudo dpkg --install ./docker-ce_18.06.1~ce~3-0~ubuntu_amd64.deb
sudo docker run hello-world
```

- Certbot renew. Reference [link](https://velog.io/@hytenic/SSL-Lets-Encrypt-Certbot-docker%EB%A5%BC-%EC%9D%B4%EC%9A%A9%ED%95%98%EC%97%AC-SSL-%EC%9D%B8%EC%A6%9D%EC%84%9C-%EB%B0%9C%EA%B8%89%EB%B0%9B%EA%B8%B0)

```
docker run --rm --name certbot -v './certbot/conf:/etc/letsencrypt' -v './certbot/logs:/var/log/letsencrypt' -v './certbot/data:/var/www/certbot' certbot/certbot:v1.20.0 renew --server https://acme-v02.api.letsencrypt.org/directory --cert-name kws1.gapmoe.net
```

```
docker run -it --rm --name certbot -v './certbot/conf:/etc/letsencrypt' -v './certbot/logs:/var/log/letsencrypt' -v './certbot/data:/var/www/certbot' certbot/certbot:v1.20.0 certificates

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -   
Found the following certs:     
  Certificate Name: kws1.gapmoe.net
.
.
.
```