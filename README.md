```
echo "deb https://raw.githubusercontent.com/proje12/pkg_ppa/master/ /" > /etc/apt/sources.list.d/pkg_ppa.list
curl   https://raw.githubusercontent.com/proje12/pkg_ppa/master/GPG.key | sudo apt-key add -
```

### Ansible adding repo

```
- name: Add key for pkg_ppa
  ansible.builtin.apt_key:
    id: AB7B03BA5646929CDB8D4C06B943C2CBF936232F
    url: https://raw.githubusercontent.com/proje12/pkg_ppa/master/GPG.key
    state: present

- name: Add pkg_ppa sources list
  ansible.builtin.apt_repository:
    repo: deb https://raw.githubusercontent.com/proje12/pkg_ppa/master/ /
    state: present
```
