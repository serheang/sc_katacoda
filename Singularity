bootstrap: docker
from:alpine:latest

%labels
  MAINTAINER Ser Heang TAN <serheang+git@gmail.com>
  WHATAMI katacoda
  VERSION 1.0

%help
  This is a container to run katacoda cli.  You just need to run the sif.  
For example:
  singularity run katacoda.sif
OR
  katacoda.sif

%environment
  export OS=$(sed -n -e 's/^ID=//p' /etc/os-release)
  export VERSION=$(sed -n -e 's/^VERSION_ID=//p' /etc/os-release)
  export LC_ALL=C
  export PATH=/usr/local/bin:$PATH

%post
  apk update
  apk add npm

  ## Get katacoda-cli via npm
  npm install katacoda-cli --global

  ## CLEANUP

%runscript
  echo "Running katacoda in ${OS}-${VERSION} container"
  katacoda $@
