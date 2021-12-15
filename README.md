## GitLab devops server docker-ansible repo (to build ansible docker images for GitLab CI/CD pipelines)

### Notes : GitLab devops server use self-signed certificate, so some hacks/workorounds

```
GitLab CI/CD pipeline (--skip-tls-verify):

    - /kaniko/executor --skip-tls-verify --context ${CI_PROJECT_DIR} --dockerfile ${CI_PROJECT_DIR}/Dockerfile --destination ${CI_REGISTRY_IMAGE}:latest

Docker daemon devops server setup:

root@devops:~/.ssh# cat /etc/docker/daemon.json 
{ "insecure-registries" : ["gitlab.devops.davar.com:2053"] }

```
