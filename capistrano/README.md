## package manger
#### rbenv

``yum install -y git-core zlib zlib-devel gcc-c++ patch readline readline-devel libyaml-devel libffi-devel openssl-devel make bzip2 autoconf automake libtool bison curl sqlite-devel``


#### ruby
``cd git clone https://github.com/rbenv/rbenv.git ~/.rbenv``

``echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc``

``echo 'eval "$(rbenv init -)"' >> ~/.bashrc``
``exec $SHELL``

``git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build``

``echo 'export PATH="$HOME/.rbenv/plugins/ruby-build/bin:$PATH"' >> ~/.bashrc``

``exec $SHELL``

``rbenv install 3.1.1``

``rbenv global 3.1.1``

``ruby -v``

#### install bundler

``gem install bundler``

``gem install capistrano``

``cap -v``

#### capistrano for magento

``gem install capistrano-magento2``

``$ cd <project_root>``

``$ mkdir -p tools/cap``

``$ cd ./tools/cap``

``$ cap install``


## Supported Tags


* `3.14`

## Example Usage

```
CAPISTRANO_VERSION=3.14

## when on macOS environments use the special ssh auth socket
if [[ $OSTYPE =~ ^darwin ]]; then
  SSH_AUTH_SOCK=/run/host-services/ssh-auth.sock
fi

docker run --rm -it -v $(pwd):/opt/capistrano -w /opt/capistrano \
  --env SSH_AUTH_SOCK=/tmp/ssh-auth.sock -v "${SSH_AUTH_SOCK:-/dev/null}":/tmp/ssh-auth.sock \
  docker.io/lalitmohann/capistrano:${CAPISTRANO_VERSION} \
  bundle exec cap stage deploy --dry-run
```

## License

This work is licensed under the MIT license. See [LICENSE](https://github.com/davidalger/warden/blob/develop/LICENSE) file for details.

## Author Information

this project is [Lalit Mohan](/)

Credit & Inspired by  [Davidalger](/)