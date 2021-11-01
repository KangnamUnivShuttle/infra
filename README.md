# infra

## Live server info

Ubuntu 14.04 LTS

Docker install progress

```
sudo apt-get install linux-image-extra-$(uname -r) linux-image-extra-virtual
wget https://download.docker.com/linux/ubuntu/dists/trusty/pool/stable/amd64/docker-ce_18.06.1~ce~3-0~ubuntu_amd64.deb
sudo dpkg --install ./docker-ce_18.06.1~ce~3-0~ubuntu_amd64.deb
sudo docker run hello-world
```

- renew
```
docker run --rm --name certbot -v './certbot/conf:/etc/letsencrypt' -v './certbot/logs:/var/log/letsencrypt' -v './certbot/data:/var/www/certbot' certbot/certbot renew --server https://acme-v02.api.letsencrypt.org/directory --cert-name kws1.gapmoe.net
```