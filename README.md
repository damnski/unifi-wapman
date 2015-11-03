/*-
 * Copyright (c) 2015 Darryl Wisneski, Finalsite Holdings Inc.
 * All rights reserved.
 *
 * Redistribution and use in source and binary forms, with or without
 * modification, are permitted provided that the following conditions
 * are met:
 * 1. Redistributions of source code must retain the above copyright
 *    notice, this list of conditions and the following disclaimer.
 * 2. Redistributions in binary form must reproduce the above copyright
 *    notice, this list of conditions and the following disclaimer in the
 *    documentation and/or other materials provided with the distribution.
 *
 * THIS SOFTWARE IS PROVIDED BY THE AUTHOR AND CONTRIBUTORS ``AS IS'' AND
 * ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
 * IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE
 * ARE DISCLAIMED.  IN NO EVENT SHALL THE AUTHOR OR CONTRIBUTORS BE LIABLE
 * FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL
 * DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS
 * OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION)
 * HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT
 * LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY
 * OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF
 * SUCH DAMAGE.
 */

An ansible automated installation of the UniFi Controller on Centos 7
and Ubuntu.

A usable server is expected to be laid out before starting, including
the effective sudo user, which implies the ssh user glue is worked out
too (i.e., SSH keys, sudo rules).

Ubiquiti, as of 201507, does not provide RPMs but does provide debs,
specifically Ubiquiti networks supports ubuntu.

#use this virtualenv for ansible-playbooks
~/ve.wapman/

# run all the playbooks
ansible-playbook -i hosts site.yml

# only run the tag
ansible-playbook -t yourtag -i hosts site.yml

# show host facts
ansible -i hosts -m setup <hostname>/<hostIP>

#TODO
- better documentation
- provide rpm .spec
- spec tests 




# unifi-wapman
