sa-secure-audit-lynis
=====================
[![Build Status](https://travis-ci.org/softasap/sa-secure-audit-lynis.svg?branch=master)](https://travis-ci.org/softasap/sa-secure-audit-lynis)


Example of use: check box-example

Installation is done via git, thus version update is achieved by `git pull`

Simple:

```YAML


     - {
         role: "sa-secure-audit-lynis"
       }

```


Advanced:

tool will try to install mailutils, if they are not installed. To gain more control over your system,
I would recommend configure system for mail sending in advance, rather than rely on defaults.
sa-postfix is one of the possible roles, included in box-example

```YAML

     - {
         role: "sa-postfix",
         tags: ["create", "update"]
       }
     - {
         role: "sa-secure-audit-lynis",
         option_install_git: false,
         lynis_version: "2.4.0",
         lynis_user: lynis

       }


```

Using lynis:

```bash

sudo lynis audit system

```


Copyright and license
---------------------

Code licensed under the [BSD 3 clause] (https://opensource.org/licenses/BSD-3-Clause) or the [MIT License] (http://opensource.org/licenses/MIT).

Subscribe for roles updates at [FB] (https://www.facebook.com/SoftAsap/)
