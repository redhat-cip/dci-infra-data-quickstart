# dci-infra-data-quickstart

## Objective

This repository goes along with [dci-infra](http://github.com/redhat-cip/dci-infra).

While [dci-infra](http://github.com/redhat-cip/dci-infra) manage all the logic of deployement, no data are store in this repository.
Datas are stored in an independent repository (like this one), that provides site specific content.

## How to use it?

One needs to fork this project, replace current data with one's own site specific needs.

Then clone this repository within the dci-infra repository and run ansible.

The succession of commands looks like

```
#> git clone http://github.com/redhat-cip/dci-infra
#> cd dci-infra
#> ansible-galaxy install -r installed_roles -p roles
#> git clone http://github.com/redhat-cip/dci-infra-data-quickstart data
#> ansible-playbook -i data/hosts playbook.yml --tags dci-core
```

After that one should have a working DCI stack up and running

## Questions?

The full documentation of the project is available at [http://doc.dci.enovance.com](http://doc.dci.enovance.com)

## How to run this on pctt

Create a `~/.config/openstack/clouds.yaml` file with your information

```
clouds:
  pctt:
    auth:
      auth_url: http://10.41.11.12:5000/v3
      project_name: <username>
      username: <username>
      password: xxxx
      user_domain_name: Default
      project_domain_name: default
```

Create a ssh key identity on PCTT, then run the ansible command with key name

    ANSIBLE_HOST_KEY_CHECKING=False ansible-playbook create_infra_on_openstack.yml --extra-vars "key_name=xxx" -i pctt_hosts
