[![Board Status](https://dev.azure.com/acherlyonok/835dceeb-f24f-4fb5-8420-f19f503b6904/dff36aaf-6df7-4871-bb9a-9569e70af1ef/_apis/work/boardbadge/60184a95-42b0-4577-93a5-652b8ac42c6c)](https://dev.azure.com/acherlyonok/835dceeb-f24f-4fb5-8420-f19f503b6904/_boards/board/t/dff36aaf-6df7-4871-bb9a-9569e70af1ef/Microsoft.RequirementCategory)
### Ansible

### Version
docker run --rm -it acherlyonok/ansible:latest --version

### Pre-requirements
docker run --rm -it -v $(pwd):/ansible -v $(pwd)/roles/:/root/.ansible/roles/ --entrypoint ansible-galaxy acherlyonok/ansible:latest install --force -r /ansible/requirements.yml

### Run
docker run --rm -it -v $(pwd):/ansible acherlyonok/ansible:latest -i /ansible/inventories/hosts.yml /ansible/main.yml -vv
docker run --rm -it -v $HOME/.ssh/:/root/.ssh/:ro -v $(pwd):/ansible acherlyonok/ansible:latest -i /ansible/inventories/hosts.yml /ansible/main.yml -vv
docker run --rm -it -v /mnt/host_home/.ssh/:/root/.ssh/:ro -v $(pwd):/ansible acherlyonok/ansible:latest -i /ansible/inventories/hosts.yml /ansible/main.yml -vv

### Debug
docker run --rm -it -v $(pwd):/ansible --entrypoint /bin/bash acherlyonok/ansible:latest
