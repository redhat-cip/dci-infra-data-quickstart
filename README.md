dci-infra-data-quickstart
=========================

Objective
---------

This repository goes along with [dci-infra](http://github.com/redhat-cip/dci-infra).

While [dci-infra](http://github.com/redhat-cip/dci-infra) manage all the logic of deployement, no data are store in this repository.
Datas are stored in an independent repository (like this one), that provides site specific content.


How to use it?
--------------

One needs to fork this project, replace current data with one's own site specific needs.

Then clone this repository within the dci-infra repository and run ansible.

The succession of commands looks like

```
#> git clone http://github.com/redhat-cip/dci-infra
#> cd dci-infra
#> git clone http://github.com/redhat-cip/dci-infra-data-quickstart data
#> ansible-playbook -i data/hosts playbook.yml --tags dci-core
```

After that one should have a working DCI stack up and running


Questions?
----------

The full documentation of the project is available at [http://doc.dci.enovance.com](http://doc.dci.enovance.com)
