## 👋 Welcome to stirlingpdf 🚀  

stirlingpdf README  
  
  
## Install my system scripts  

```shell
 sudo bash -c "$(curl -q -LSsf "https://github.com/systemmgr/installer/raw/main/install.sh")"
 sudo systemmgr --config && sudo systemmgr install scripts  
```
  
## Automatic install/update  
  
```shell
dockermgr update stirlingpdf
```
  
## Install and run container
  
```shell
mkdir -p "$HOME/.local/share/srv/docker/stirlingpdf/rootfs"
git clone "https://github.com/dockermgr/stirlingpdf" "$HOME/.local/share/CasjaysDev/dockermgr/stirlingpdf"
cp -Rfva "$HOME/.local/share/CasjaysDev/dockermgr/stirlingpdf/rootfs/." "$HOME/.local/share/srv/docker/stirlingpdf/rootfs/"
docker run -d \
--restart always \
--privileged \
--name casjaysdevdocker-stirlingpdf \
--hostname stirlingpdf \
-e TZ=${TIMEZONE:-America/New_York} \
-v "$HOME/.local/share/srv/docker/casjaysdevdocker-stirlingpdf/rootfs/data:/data:z" \
-v "$HOME/.local/share/srv/docker/casjaysdevdocker-stirlingpdf/rootfs/config:/config:z" \
-p 80:80 \
casjaysdevdocker/stirlingpdf:latest
```
  
## via docker-compose  
  
```yaml
version: "2"
services:
  ProjectName:
    image: casjaysdevdocker/stirlingpdf
    container_name: casjaysdevdocker-stirlingpdf
    environment:
      - TZ=America/New_York
      - HOSTNAME=stirlingpdf
    volumes:
      - "$HOME/.local/share/srv/docker/casjaysdevdocker-stirlingpdf/rootfs/data:/data:z"
      - "$HOME/.local/share/srv/docker/casjaysdevdocker-stirlingpdf/rootfs/config:/config:z"
    ports:
      - 80:80
    restart: always
```
  
## Get source files  
  
```shell
dockermgr download src casjaysdevdocker/stirlingpdf
```
  
OR
  
```shell
git clone "https://github.com/casjaysdevdocker/stirlingpdf" "$HOME/Projects/github/casjaysdevdocker/stirlingpdf"
```
  
## Build container  
  
```shell
cd "$HOME/Projects/github/casjaysdevdocker/stirlingpdf"
buildx 
```
  
## Authors  
  
🤖 casjay: [Github](https://github.com/casjay) 🤖  
⛵ casjaysdevdocker: [Github](https://github.com/casjaysdevdocker) [Docker](https://hub.docker.com/u/casjaysdevdocker) ⛵  
