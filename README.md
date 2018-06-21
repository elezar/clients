# DC/OS Client images

This repository contains a collection of clients for a selection of DC/OS data services.

## Building the images

```bash
TAG=$( git rev-parse --short HEAD )
docker build -t elezar/${SERVICE}-client:${TAG} ${SERVICE}
docker push elezar/${SERVICE}-client:${TAG}
```
where `SERVICE` is one of the subfolders of this folder.
