# docker-ansible-core

[docker-ansible-core](https://github.com/ju2wheels/docker-ansible-core) provides
[ju2wheels/ansible-core](https://hub.docker.com/r/ju2wheels/ansible-core/) Docker Hub images for containers that are capable
of being used for both unit testing (by running Ansible against the local container as if it were a remote machine) as well as
being suitable for use as an Ansible host. In addition to the ansibe-core 2.11.x (aka
[Ansible 4](https://github.com/ansible-community/ansible-build-data/blob/main/4/CHANGELOG-v4.rst) ), ansibe-core 2.12.x (aka
[Ansible 5](https://github.com/ansible-community/ansible-build-data/blob/main/5/CHANGELOG-v5.rst) ), ansibe-core 2.13.x (aka
[Ansible 6](https://github.com/ansible-community/ansible-build-data/blob/main/6/CHANGELOG-v6.rst) ), or ansibe-core 2.14.x (aka
[Ansible 7](https://github.com/ansible-community/ansible-build-data/blob/main/7/CHANGELOG-v7.rst) ) these images include some
dependencies for main common collections installed from PyPi using Python 3.x at the user level instead of at the system level
so as to minimize conflicts with system Python packages leveraging the system supported versions of Python 3.x .

## WARNING

Ansible 4 supports Python 3.5 or greater, however there is a runtime behavior difference when running with Python 3.5 vs when
running with Python 3.6 or greater because Jinaja2 3.x only supports Python 3.6 or greater. Therefore if you run Ansible on
Python 3.5, it will fallback to Jinja2 2.x and cause a different runtime behavior.

Ansible 5 and 6 requires Python 3.8 or greater, while Ansible 7 or higher requires Python 3.9 or greater.

We do not recommend using Python 3.5 with Ansible 4 on your controller host (the host that initially runs Ansible).

For the Docker images below, if the Python 3 system default version was less than 3.6, we have installed Python 3.6 or newer
and used that to install Ansible 4.

For the Docker images below, if the Python 3 system default version was less than 3.8, we have installed Python 3.8 or newer
and used that to install Ansible 5 and 6.

For the Docker images below, if the Python 3 system default version was less than 3.9, we have installed Python 3.8 or newer
and used that to install Ansible 7 or higher.

## Available Docker Image Tags

The `ju2wheels/ansible-core` Docker image tags follow the naming convention that includes the following items joined with `-`:

1. The Ansible major version (ie `2.11.x` since we always install the latest minor version).
2. The Linux distribution name.
3. The Linux distribution version.
4. The Docker image platform if other than `linux/amd64`.

|2.11.x Docker Image Tags  |Platform Architecture      |
|--------------------------|---------------------------|
|2.11.x-alpine-3.14        |linux/amd64, linux/arm64/v8|
|2.11.x-alpine-3.15        |linux/amd64, linux/arm64/v8|
|2.11.x-alpine-3.16        |linux/amd64, linux/arm64/v8|
|2.11.x-amazonlinux-2      |linux/amd64, linux/arm64/v8|
|2.11.x-amazonlinux-2022   |linux/amd64, linux/arm64/v8|
|2.11.x-debian-10          |linux/amd64, linux/arm64/v8|
|2.11.x-debian-11          |linux/amd64, linux/arm64/v8|
|2.11.x-fedora-36          |linux/amd64, linux/arm64/v8|
|2.11.x-fedora-37          |linux/amd64, linux/arm64/v8|
|2.11.x-linuxmint-19.3     |linux/amd64                |
|2.11.x-linuxmint-20.3     |linux/amd64                |
|2.11.x-linuxmint-21.1     |linux/amd64                |
|2.11.x-opensuse-15.4      |linux/amd64, linux/arm64/v8|
|2.11.x-opensuse-tumbleweed|linux/amd64, linux/arm64/v8|
|2.11.x-ubuntu-18.04       |linux/amd64, linux/arm64/v8|
|2.11.x-ubuntu-20.04       |linux/amd64, linux/arm64/v8|
|2.11.x-ubuntu-22.04       |linux/amd64, linux/arm64/v8|

|2.12.x Docker Image Tags  |Platform Architecture      |
|--------------------------|---------------------------|
|2.12.x-alpine-3.14        |linux/amd64, linux/arm64/v8|
|2.12.x-alpine-3.15        |linux/amd64, linux/arm64/v8|
|2.12.x-alpine-3.16        |linux/amd64, linux/arm64/v8|
|2.12.x-amazonlinux-2      |linux/amd64, linux/arm64/v8|
|2.12.x-amazonlinux-2022   |linux/amd64, linux/arm64/v8|
|2.12.x-debian-10          |linux/amd64, linux/arm64/v8|
|2.12.x-debian-11          |linux/amd64, linux/arm64/v8|
|2.12.x-fedora-36          |linux/amd64, linux/arm64/v8|
|2.12.x-fedora-37          |linux/amd64, linux/arm64/v8|
|2.12.x-linuxmint-19.3     |linux/amd64                |
|2.12.x-linuxmint-20.3     |linux/amd64                |
|2.12.x-linuxmint-21.1     |linux/amd64                |
|2.12.x-opensuse-15.4      |linux/amd64, linux/arm64/v8|
|2.12.x-opensuse-tumbleweed|linux/amd64, linux/arm64/v8|
|2.12.x-ubuntu-18.04       |linux/amd64, linux/arm64/v8|
|2.12.x-ubuntu-20.04       |linux/amd64, linux/arm64/v8|
|2.12.x-ubuntu-22.04       |linux/amd64, linux/arm64/v8|

|2.13.x Docker Image Tags  |Platform Architecture      |
|--------------------------|---------------------------|
|2.13.x-alpine-3.14        |linux/amd64, linux/arm64/v8|
|2.13.x-alpine-3.15        |linux/amd64, linux/arm64/v8|
|2.13.x-alpine-3.16        |linux/amd64, linux/arm64/v8|
|2.13.x-amazonlinux-2      |linux/amd64, linux/arm64/v8|
|2.13.x-amazonlinux-2022   |linux/amd64, linux/arm64/v8|
|2.13.x-debian-10          |linux/amd64, linux/arm64/v8|
|2.13.x-debian-11          |linux/amd64, linux/arm64/v8|
|2.13.x-fedora-36          |linux/amd64, linux/arm64/v8|
|2.13.x-fedora-37          |linux/amd64, linux/arm64/v8|
|2.13.x-linuxmint-19.3     |linux/amd64                |
|2.13.x-linuxmint-20.3     |linux/amd64                |
|2.13.x-linuxmint-21.1     |linux/amd64                |
|2.13.x-opensuse-15.4      |linux/amd64, linux/arm64/v8|
|2.13.x-opensuse-tumbleweed|linux/amd64, linux/arm64/v8|
|2.13.x-ubuntu-18.04       |linux/amd64, linux/arm64/v8|
|2.13.x-ubuntu-20.04       |linux/amd64, linux/arm64/v8|
|2.13.x-ubuntu-22.04       |linux/amd64, linux/arm64/v8|

|2.14.x Docker Image Tags  |Platform Architecture      |
|--------------------------|---------------------------|
|2.14.x-alpine-3.14        |linux/amd64, linux/arm64/v8|
|2.14.x-alpine-3.15        |linux/amd64, linux/arm64/v8|
|2.14.x-alpine-3.16        |linux/amd64, linux/arm64/v8|
|2.14.x-amazonlinux-2      |linux/amd64, linux/arm64/v8|
|2.14.x-amazonlinux-2022   |linux/amd64, linux/arm64/v8|
|2.14.x-debian-10          |linux/amd64, linux/arm64/v8|
|2.14.x-debian-11          |linux/amd64, linux/arm64/v8|
|2.14.x-fedora-36          |linux/amd64, linux/arm64/v8|
|2.14.x-fedora-37          |linux/amd64, linux/arm64/v8|
|2.14.x-linuxmint-19.3     |linux/amd64                |
|2.14.x-linuxmint-20.3     |linux/amd64                |
|2.14.x-linuxmint-21.1     |linux/amd64                |
|2.14.x-opensuse-15.4      |linux/amd64, linux/arm64/v8|
|2.14.x-opensuse-tumbleweed|linux/amd64, linux/arm64/v8|
|2.14.x-ubuntu-18.04       |linux/amd64, linux/arm64/v8|
|2.14.x-ubuntu-20.04       |linux/amd64, linux/arm64/v8|
|2.14.x-ubuntu-22.04       |linux/amd64, linux/arm64/v8|

## Organization of `Dockerfile`s

Each image `Dockerfile` has its commands organized as follows:

1. Set environment variables for `PATH` and any environment variables required for building the Python modules we will install.
2. System updates (update all packages that came in the base distro image).
3. Supplemental repository setup.
4. Install base development tools and any packages that we want included in our images to make Ansible work.
5. Install development libraries that are required to build Python modules we want to install (including Ansible) but that we intend to remove from the final image.
6. Install pip, Ansible, and other Ansible dependencies from PyPi at the user level (root).
7. Uninstall the development libraries required to install Python modules.
8. Delete caches and temporary files.
9. Set the default `entrypoint` to `ansible-playbook`.

Note: We install Ansible at the user level instead of a virtualenv because some of the Python modules can only be installed via distro packages
and not from PyPi and this allows the system level Python packages to be seen by default. Therefore by installing a global Python 3.x on the distro and
those dependencies using the system packaging we can still access them by installing Ansible and all other dependencies at the user level while not cluttering
up the system level Python packages or potentially crippling the system. While this can be done with a virtualenv, we isolated it under the root user instead as
we dont need to run Ansible from multiple users.

## Using The Containers As Ansible Hosts

By default, all the images have their `entrypoint` configured as `ansible-playbook` for use as unit test containers.

In order to run the container as an Ansible host you will have to do the following:

1. Override the `entrypoint` to a proper shell such as `/bin/bash`.
2. Mount your Ansible playbook directory as a `VOLUME`.
3. Optionally set the `ANSIBLE_CONFIG` and `ANSIBLE_INVENTORY` environment variables.

Using the CLI:

```
docker run --entrypoint /bin/bash                                   \
           --env ANSIBLE_CONFIG=/ansible-playbook/ansible.cfg       \
           --env ANSIBLE_INVENTORY=/ansible-playbook/inventory      \
           --volume '/home/user/ansible-playbook:/ansible-playbook' \
           -it ju2wheels/ansible-core:<tag>
```


Using a `docker-compose` file:

```
version: '2'
services:
  ansible_host:
    entrypoint: /bin/bash
    environment:
      ANSIBLE_CONFIG:    /ansible-playbook/ansible.cfg
      ANSIBLE_INVENTORY: /ansible-playbook/inventory
    image: ju2wheels/ansible-core:<tag>
    tty: true
    volumes:
      # If you place this docker-compose.yml in the root of your ansible-playbook directory
      # then you can make the volume path relative instead of absolute
      #- ./:/ansible-playbook
      - /home/user/ansible-playbook:/ansible-playbook
```

You can then run `docker-compose`:

```
docker-compose run ansible_host

# From inside the docker container
cd /ansible-playbook
ansible-playbook my-playbook.yml
```

## Using The Containers For Ansible Role Unit Testing

For the following unit test examples, we assume that your Ansible role meets the following conditions:

1. The role is modeled after an Ansible 2.11.x role as created by `ansible-galaxy init`, for example:
    ```
    $ ansible-galaxy init testrole
    $ find testrole
    testrole/
    testrole/README.md
    testrole/templates
    testrole/.travis.yml
    testrole/handlers
    testrole/handlers/main.yml
    testrole/meta
    testrole/meta/main.yml
    testrole/tests
    testrole/tests/test.yml
    testrole/tests/inventory
    testrole/tasks
    testrole/tasks/main.yml
    testrole/vars
    testrole/vars/main.yml
    testrole/defaults
    testrole/defaults/main.yml
    testrole/files
    ```
2. The role's tests directory has had an ansible.config and inventory added, and roles directory with a role that is relatively symlinked back to the main role directory,
   and an ansible_requirements.yml file to get needed dependency collections and roles:
    ```
    $ cd testrole

    # Add necessary GIT ignores (dont include the collections or the symlink to the current role
    # (be sure not to delete that symlink when deleting/updating roles)
    $ cat <<EOF > .gitignore
    *~
    *.pyc
    *.retry
    tests/collections/
    tests/roles/*
    !tests/roles/testrole
    EOF

    # Setup tests directory structure and files

    $ mkdir tests
    $ cd tests

    $ cat <<EOF > ansible.cfg
    [defaults]
    collections_paths          = ./collections:~/.ansible/collections:/usr/share/ansible/collections:/etc/ansible/collections
    executable                 = /bin/bash
    interpreter_python         = /usr/bin/python3
    inventory                  = ./inventory
    nocolor                    = 1
    retry_files_enabled        = False
    roles_path                 = ./roles:~/.ansible/roles:/usr/share/ansible/roles:/etc/ansible/roles
    transport                  = local

    [privilege_escalation]
    # Docker only has su available by default (although we install sudo into the Docker images above).
    # If you try to run this inside something other than Docker or you have already installed sudo, then
    # switch this back to `sudo` or simply remove it.
    become_method = su
    EOF

    $ cat <<EOF > inventory
    # At a minimum, we need localhost and we need to set ansible_python_interpreter
    # because not all the Docker images default to Python 3.x as the default Python
    localhost ansible_connection=local ansible_python_interpreter=/usr/bin/python3
    EOF

    # Create a symlink to the current role since ansible-galaxy requuirements file format doesnt allow
    # using a local file directory as a source for roles.
    $ mkdir roles
    $ cd roles
    $ ln -s ../../ testrole
    $ cd ..

    # You should run the following each time you need to update the dependencies before running any tests:
    #   $ cd tests/
    #   $ ansible-galaxy install -r ansible_requirements.yml
    $ cat <<EOF > ansible_requirements.yml
    ---

    collections:
      # - name:    community.general          # namespace_name.collection_name
      #   source:  https://galaxy.ansible.com # The Galaxy URL to pull the collection from (default: ``--api-server`` from cmdline), optional
      #   type:    galaxy                     # file, galaxy, git, url
      #   version: 2.5.2                      # version range identifiers (default: ``*``)
      # - name:    community.general                                            # namespace_name.collection_name
      #   source:  https://github.com/ansible-collections/community.general.git # Repository URL
      #   type:    git                                                          # file, galaxy, git, url
      #   version: 3.5.0                                                        # git commit-ish

      # Ansible curated stable (see https://github.com/ansible-community/ansible-build-data/blob/main/4/CHANGELOG-v4.rst)
      - name: community.general
        version: 2.5.2
      - name: community.docker
        version: 1.6.0

    roles:
      # - name:    ansible-core                                    # namespace.role_name
      #   scm:     git                                             # git, hg
      #   src:     git@gitlab.company.com:mygroup/ansible-core.git # url or namespace.role_name
      #   version: 1.0                                             # version or git commit-ish
      []
    EOF
    ```


Using the above role structure, all we have to do is add a `docker_test.yml` playbook file to our role's `tests/` directory that
runs the `docker_container` module (Ansible 2.11.x) (see below) to execute the `test.yml` playbook inside of one of our Docker
containers.

Using Ansible 2.11.x `docker_test.yml` may look like this:

```
---

- hosts: localhost
  tasks:
    - name: testrole dockerized unit test
      community.docker.docker_container:
        cleanup: true
        command: /ansible-playbook/tests/test.yml
        detach: false
        entrypoint: ansible-playbook
        env:
          ANSIBLE_CONFIG:    /ansible-playbook/tests/ansible.cfg
          ANSIBLE_INVENTORY: /ansible-playbook/tests/inventory
          ANSIBLE_NOCOLOR:   1
        hostname: ansible_testrole_test
        image: "{{ item }}"
        interactive: true
        name: ansible_testrole_test
        pull: true
        recreate: true
        restart_policy: false
        state: started
        tty: true
        volumes:
          - "{{ playbook_dir }}/../:/ansible-playbook"
      loop:
        - ju2wheels/ansible-core:2.11.x-ubuntu-16.04
        - ju2wheels/ansible-core:2.11.x-ubuntu-18.04
        - ju2wheels/ansible-core:2.11.x-ubuntu-20.04
```

You can then run `docker_test.yml` to kick off your unit tests:

```
cd testrole/tests
ansible-playbook docker_test.yml
```

Alternatively, you ran do a single run manaully without using `docker_test.yml`:

```
docker run --env ANSIBLE_CONFIG=/ansible-playbook/ansible.cfg       \
           --env ANSIBLE_INVENTORY=/ansible-playbook/inventory      \
           --volume '/home/user/ansible-playbook:/ansible-playbook' \
           -it ju2wheels/ansible-core:<tag> [<ansible-playbook ARGS>] <playbook.yml>
```

Note: In order to run the the unit tests, you will need the following installed on the host running the tests:

* ansible
* docker
* docker Python module (or docker-py for older versions of Docker)

Note: I have tried to ensure all Ansible core module dependencies are installed in these images, however, since I can't test each individual module
there may be instances where dependencies may have been missed. If you encounter a missing dependency or would like to see dependencies for commonly
used third party Ansible modules, please open an [issue](https://github.com/ju2wheels/docker-ansible-core/issues) and include the Ansible version you
are using, the Docker image name, the Ansible module name, and a description of the dependencies required by that module.

## Running Ansible As Another User

Since Ansible is installed at the user level, only the root user in these containers can run Ansible.

If you want to add another user under which to run Ansible you will have to copy the root user's `HOME` directory:

```
useradd -m newuser
cp -ar /root/. /home/newuser/
chown -R newuser:newuser /home/newuser
echo 'export PATH=/home/newuser/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin' >> /home/newuser/.bashrc
```

## Contributing

Contributions of additional platforms or updates to Ansible module dependencies are welcome. Please open an
[issue](https://github.com/ju2wheels/docker-ansible-core/issues) first before submitting a PR.

## License

GPLv2

## Author

Julio Lajara \<First.Last at Protonmail>
