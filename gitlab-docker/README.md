# Ansible Playbooks for building/deploying GitLab on Docker

There are two Ansible Playbooks one for building a Docker image from the GitLab source code, and the other for running GitLab on Docker from the Docker Hub:

  - build-image
  - run-from-docker-hub

# Building GitLab from source and deploying to Docker using Ansible

Edit the `hosts` inventory file to point to the server(s) you want to deploy to.

```
[web]
172.0.0.0
```

This hosts file will deploy to `172.0.0.0`, edit to point to the correct server(s). GitLab can be deployed using the following command:

```
ansible-playbook -i hosts gitlab.yml
```

GitLab can be reached by browsing to `http://172.0.0.0:8080`

If you only want to build the images and not run them, use the `--skip-tags` flag to skip sections. For example:

```
ansible-playbook -i hosts gitlab.yml --skip-tags "run"
```
