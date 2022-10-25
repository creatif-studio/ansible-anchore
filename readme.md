# Anchore Ansible Role

Convert docker compose to ansible roles

# Requirements

- ansible
- vagrant
- virtualbox

# How to run in local vm?

- go to vagrant directory `cd vagrant` and `vagrant up`
- run this command `vagrant ssh-config > vagrant-ssh`
- cat the private key in this path `IdentityFile`
- replace `files/ssh.key` with the value above
- replace ip in `ansible.host` with `192.168.56.2`
- run `ansible-playbook ansible.yml`

# How to run in server?

- replace ip in ansible.host with `192.168.56.2`
- change `ansible_user` in `group_vars/all.yml` with real user
- replace ssh-key in `files/ssh.key` with real ssh key
- optional: uncomment ansible_ssh_pass, ansible_sudo_pass and replace `password` with your password server
- run `ansible-playbook ansible.yml`
