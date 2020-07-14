# ansible-inventory-template

ansible-inventory-template

 - Get the corresponding perfSONAR Ansible playbook and bootstrap it

```
git clone playbook
cd playbook
ansible-galaxy install -r  requirements.yml --ignore-errors
```

 - add this repository to the perfSONAR Ansible playbook

```
git clone inventory
```

 - Use Ansible ping to verify connectivity to targets.  ssh and become passwords are Kerberos.

```
ansible \
  --ask-pass \
  --ask-become-pass  \
  --ask-vault-pass \
  -i ansible-inventory-template/inventory \
  all -m ping
```

 - Run master playbook

```
ansible-playbook \
  --ask-pass \
  --ask-become-pass  \
  --ask-vault-pass \
  -i ansible-inventory-template/inventory \
  playbook.yml
```

 - Run locl playbook

```
ansible-playbook \
  --ask-pass \
  --ask-become-pass  \
  --ask-vault-pass \
  -i ansible-inventory-template/inventory \
  ansible-inventory-template/playbooks/local_playbook.yml
```
