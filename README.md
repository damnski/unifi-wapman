# unifi-wapman

## About

An ansible automated installation of the UniFi Controller.

A usable server is expected to be laid out before starting, including
the effective sudo user, which implies the ssh user glue is worked out
too (i.e., SSH keys, sudo rules).

Ubiquiti, as of 201507, does not provide RPMs but does provide debs,
specifically Ubiquiti networks supports ubuntu.  This playbook pulls down the zip provided by Ubiquiti so it should work on ubuntu as well.

A systemd startup script is included, so this playbook is largely linux
distro agnostic

## Example Usage

virtualenv for ansible-playbooks:

    ~/ve.wapman/

run all the playbooks:

    ansible-playbook -i hosts site.yml

only run the tag, convenient for running discreet tagged plays within the playbook:

    ansible-playbook -t yourtag -i hosts site.yml

show host facts:

    ansible -i hosts -m setup <hostname>/<hostIP>

## Todo

- better documentation
- provide rpm .spec
- ubuntu and debian, specific broken out package dependecies

## Caveats
Tested on Centos 7
