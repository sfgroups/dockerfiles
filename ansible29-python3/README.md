# ansible 2.9.0 python3 

Dockerfile to create python3 with Ansible .2.9

docker build -t sfgroups/ansible-python3 .

docker run --rm --name ansible -it sfgroups/ansible-python3 ansible --version

docker run --rm -it \
        --name ansible \
        -v ~/.ssh:/root/.ssh:ro \
        -v ~/.kube:/.kube \
        -v $(pwd):/playbooks \
        sfgroups/ansible-python3

ansible -i hosts all -m ping 
ansible -i hosts all -m setup



mkdir out
ansible -m setup --tree out/ all
ansible-cmdb out/ > overview.html
ansible-cmdb -t html_fancy_split -i hosts out/
