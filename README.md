# Ansible Role: NTP

Installs NTP on Linux.

## Requirements

None.

## Role Variables

Set the timezone for your server:
    ntp_timezone: Etc/UTC


Set the [NTP Pool Area](http://support.ntp.org/bin/view/Servers/NTPPoolServers) to use. Defaults to none, which uses the worldwide pool.

    ntp_servers:
      - "0{{ ntp_area }}.pool.ntp.org iburst"
      - "1{{ ntp_area }}.pool.ntp.org iburst"
      - "2{{ ntp_area }}.pool.ntp.org iburst"
      - "3{{ ntp_area }}.pool.ntp.org iburst"

Restrict NTP access to these hosts; loopback only, by default:
    ntp_restrict:
      - "127.0.0.1"
      - "::1"

## Dependencies

None.

## Example Playbook

    - hosts: all
      roles:
        - role:         mikev1963.ntp
          ntp_timezone: America/New_York
          ntp_area:     'north-america'

*Inside `defaults/main.yml`*:

    ntp_timezone:   America/New York
    ntp_area:       'north-america'


## Author Information

This role was created in 2018 by [Michael Ventarola]
