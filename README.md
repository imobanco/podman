# podman

## Instalação do podman


```bash
. /etc/os-release \
&& echo "deb https://download.opensuse.org/repositories/devel:/kubic:/libcontainers:/stable/xUbuntu_${VERSION_ID}/ /" | sudo tee /etc/apt/sources.list.d/devel:kubic:libcontainers:stable.list \
&& curl -L https://download.opensuse.org/repositories/devel:/kubic:/libcontainers:/stable/xUbuntu_${VERSION_ID}/Release.key | sudo apt-key add - \
&& sudo apt-get update \
&& sudo apt-get -y upgrade \
&& sudo apt-get -y install podman
```
Fonte: [podman.io/getting-started/installation](https://podman.io/getting-started/installation)


### Testando a instalação do podman

```bash
podman \
run \
--interactive=true \
--tty=true \
--rm=true \
--workdir=/code \
--volume="$(pwd)":/code \
ubuntu:20.04 \
bash -c 'apt-get update && apt-get install -y hello && hello'
```

