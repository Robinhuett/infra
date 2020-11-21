# Ansible stuff for my own infrastructure

> There shouldn't be too much to see here.

## What can this playbook do for me?
- Automagicaly deploy changes to the servers.
- Spin up servers that are defined in the `inventory` file.
- Configure the DNS records for said servers.
- Deploying the services outlined below.

## What can I do for this playbook?
- After the initial deployment you should [export your borgbackup keys](https://borgbackup.readthedocs.io/en/stable/usage/key.html#borg-key-export).
  - `borg [common options] key export [options] [REPOSITORY] [PATH]`
- For Mailu the following has to be set up:
  - [Generate DKIM and setup DNS accordingly](https://mailu.io/1.7/dns.html?highlight=dkim#dkim-spf-dmarc-entries)
  - Additional domains
  - Additional accounts/aliases
- In nextcloud you can (and probably want to) configure:
  - Mailu as user backend to have only one place to manage users
    - [Backend config](https://mailu.io/1.7/faq.html#i-want-to-integrate-nextcloud-15-and-newer-with-mailu)
    - `'lost_password_link' => 'https://place.to.reset/your/mailu/password`
- In Grafana you can and (probably want to) configure:
  - Configure dashboards
    - *Those will come preconfigured when I decided on some layouts*

## Things this playbook won't do, even with when asked nicely:
- Removing servers when they aren't needed anymore.
- Currently this playbook is only targeted for debian-10.
- Making coffee ☕️

## Running services:
- Mail with [Mailu](https://mailu.io/)
- Reverse Proxy with [Nginx](https://nginx.com/)
- Filesharing with [Nextcloud](https://nextcloud.com/)
- Backups with [Borgbackup](https://www.borgbackup.org/) to [rsync.net](https://rsync.net)
- Log aggregation with [Grafana Loki](https://grafana.com/oss/loki/)
- Torrent Tracker with [chihaya](https://github.com/chihaya/chihaya)
- Some of my own stuff

## Features for Future
- Use Docker Swarm
