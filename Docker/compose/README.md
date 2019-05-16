```
sudo docker build -t anrdoird.image -f ./Dockerfile .
sudo docker images
sudo docker tag 33b442f60543 payly/android-gitlab-ci:1.0.2
sudo docker push payly/android-gitlab-ci:1.0.2
sudo docker save payly/android-gitlab-ci:1.0.2 > android-gitlab-ci-v1.0.2.tar
sudo docker load --input android-gitlab-ci-v1.0.2.tar
```

### Remover todos containers

```shell
sudo docker rm $(docker ps -a -q)
```

### Limpa disco

```shell
0 5 * * * root /usr/bin/docker system prune --all --volumes --force >/dev/null
```

### Restart Docker

```shell
sudo systemctl restart docker
```
