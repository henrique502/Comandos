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

### Postgres

[Referência](https://medium.com/@renato.groffe/postgresql-docker-executando-uma-inst%C3%A2ncia-e-o-pgadmin-4-a-partir-de-containers-ad783e85b1a4)

```shell
sudo docker network create --driver bridge postgres-network
docker run --name local-postgres --network=postgres-network -e "POSTGRES_PASSWORD=root" -p 5432:5432 -v /home/{USER}/.PostgreSQL:/var/lib/postgresql/data -d postgres
```
