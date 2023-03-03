<p align="center">
  <a href="https://github.com/creatif-studio/ansible-anchore">
    <img alt="ansible-anchore" width="75px" height="75px" src="./assets/logo.png">
  </a>
</p>

<p align="center">
  Deploy and manage Anchore with ease using our Ansible playbook
</p>

# Requirements

- ansible
- vagrant
- virtualbox

# How to run in local vm?

- go to vagrant directory `cd vagrant` and `vagrant up`
- run this command `vagrant ssh-config > vagrant-ssh`
- `cat` the private key in this path `IdentityFile`
- replace `files/ssh.key` with the value above
- replace ip in `ansible.host` with `192.168.56.2`
- run `ansible-playbook ansible.yml --tags "install-docker"`
- run `ansible-playbook ansible.yml --tags "install-network"`
- run `ansible-playbook ansible.yml --tags "install-anchore"`

# How to run in server?

- replace ip in ansible.host with `192.168.56.2`
- change `ansible_user` in `group_vars/global.yml` with real user
- replace ssh-key in `files/ssh.key` with real ssh key
- optional: uncomment ansible_ssh_pass, ansible_sudo_pass and replace `password` with your password server
- run `ansible-playbook ansible.yml --tags "install-docker"`
- run `ansible-playbook ansible.yml --tags "install-network"`
- run `ansible-playbook ansible.yml --tags "install-anchore"`
