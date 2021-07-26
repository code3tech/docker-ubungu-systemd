# Docker ubuntu Systemd

[![](https://img.shields.io/badge/Code3%20Tech-DevOps%20Tool-%231D8348)](https://hub.docker.com/repository/docker/code3tech/ubuntu)
[![](https://img.shields.io/docker/cloud/automated/code3tech/ubuntu)](https://hub.docker.com/repository/docker/code3tech/ubuntu)
[![](https://img.shields.io/docker/cloud/build/code3tech/ubuntu)](https://hub.docker.com/repository/docker/code3tech/ubuntu)
[![](https://img.shields.io/docker/image-size/code3tech/ubuntu/stretch)](https://hub.docker.com/repository/docker/code3tech/ubuntu)
[![](https://img.shields.io/docker/pulls/code3tech/ubuntu)](https://hub.docker.com/repository/docker/code3tech/ubuntu)
[![](https://img.shields.io/docker/stars/code3tech/ubuntu)](https://hub.docker.com/repository/docker/code3tech/ubuntu)
[![](https://img.shields.io/github/issues/code3tech/docker-ubuntu-systemd)](https://hub.docker.com/repository/docker/code3tech/ubuntu)
[![](https://img.shields.io/github/license/code3tech/docker-ubuntu-systemd)](https://hub.docker.com/repository/docker/code3tech/ubuntu)

Este Dockerfile pode construir containers com a capacidade de usar o systemd, seu principal proposito é testar ansible playbooks e roles, simulando o SO alvo.

Branches
------------

Para facilitar a manutenção e atualização desses containers decidimos adotar uma estratégia de multiplas branches que refletem as versions do sistema operacional alvo. Dessa forma cada branch reflete uma versão do SO, como demostrado na tabela abaixo:

|Branch    |Ubuntu Version        |Docker image tag     |
|----------|----------------------|---------------------|
|main      |latest (bullseye/11)  |latest               |
|buster    |buster                |buster               |
|stretch   |stretch               |stretch              |

Pull strategy
------------

Cada branch nesse repositório tem um ciclo de vida individual, portanto **NÃO** se deve fazer merged.

Como Usar
------------

Rodando a última versão da imagem docker.

```
docker run \
  --tty \
  --privileged \
  --volume /sys/fs/cgroup:/sys/fs/cgroup:ro \
  --volume /tmp:/tmp \
  code3tech/ubuntu
```

Rodando uma versão específica da imagem docker.

```
docker run \
  --tty \
  --privileged \
  --volume /sys/fs/cgroup:/sys/fs/cgroup:ro \
  --volume /tmp:/tmp \
  code3tech/ubuntu:focal
``` 

Construindo seu própria imagem docker
------------

Para construir o sua própria imagem docker siga os seguintes passos:

  1. [Instale Docker](https://docs.docker.com/engine/installation/).
  2. Faça o clone do repositório para sua área de trabalho `git clone https://github.com/code3tech/docker-ubuntu-systemd.git`
  3. Entre no diretório `cd docker-ubuntu-systemd`
  4. Execute o commando para construir a imagem `docker build -t my-ubuntu .`
  5. Execute o commando para rodar `docker run --tty --privileged -v /sys/fs/cgroup:/sys/fs/cgroup:ro -v /tmp:/tmp my-ubuntu`

Author
------------

Created in 2021 by [Code3 Tech](https://code3.tech/) 