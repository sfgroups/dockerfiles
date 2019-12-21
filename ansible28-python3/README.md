# ansible 2.9.0 python3 

Dockerfile to create python3 with Ansible .2.9

docker build -t ansible-python3 .

docker run --rm --name ansible -it ansible-python3 ansible --version
ansible 2.9.2
  config file = None
  configured module search path = ['/root/.ansible/plugins/modules', '/usr/share/ansible/plugins/modules']
  ansible python module location = /usr/local/lib/python3.9/site-packages/ansible
  executable location = /usr/local/bin/ansible
  python version = 3.9.0a1 (default, Dec 11 2019, 00:42:23) [GCC 8.3.0]

