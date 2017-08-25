# unifi-wapman

## About

An ansible automated installation of the UniFi Controller for Centos and *linux* 

A usable server is expected to be laid out before starting, including
the effective sudo user, which implies the ssh user glue is worked out
too (i.e., SSH keys, sudo rules).

Ubiquiti, as of 201507, does not provide RPMs but does provide debs,
specifically Ubiquiti networks supports ubuntu.  This playbook pulls
down the zip provided by Ubiquiti so it should work on ubuntu as well.

^^^ This is still the situation as of 201708,
but they still provide releases via UniFi.unix.zip
(http://dl.ubnt.com/unifi/4.7.5/UniFi.unix.zip).

A systemd startup script is included, so this playbook is largely linux
distro agnostic

Upgrade from 4.7.5 to 5.5.20:
  - make a backup from web interface
  - sudo systemctl stop unifi.service
  - move the /opt/Unify directory out of the way
  - move the /usr/local/src/UniFi.unix.zip out of the way
  - sudo yum remove java-1.7.0-openjdk-headless java-1.7.0-openjdk
  - run ansible
  - restore to latest backup from web interface
  - the daemon seems to die, verify this, then restart:
    sudo systemctl start unifi.service
  - it seems the APs will restart when acquired/provisioned.

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
- upgrades are cumbersome

## Caveats
Tested on Centos 7
