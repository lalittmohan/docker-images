# Ansible Docker Images

## Supported Tags

* `2.4`
* `2.5`
* `2.6`
* `2.7`
* `2.8`
* `2.9`

## Example Usage

```
ANSIBLE_VERSION=2.9

## when on macOS environments use the special ssh auth socket
if [[ $OSTYPE =~ ^darwin ]]; then
  SSH_AUTH_SOCK=/run/host-services/ssh-auth.sock
fi

docker run --rm -it -v $(pwd):/opt/ansible -w /opt/ansible \
  --env SSH_AUTH_SOCK=/tmp/ssh-auth.sock -v "${SSH_AUTH_SOCK:-/dev/null}":/tmp/ssh-auth.sock \
  --env ANSIBLE_REMOTE_USER="$(whoami)" docker.io/lalitmohann/ansible:${ANSIBLE_VERSION} \
  ansible-playbook -i inventory playbook.yml --tags users --diff
```

## License


## Author Information


