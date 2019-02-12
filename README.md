# Ansible Role: NTP

Installs NTP on Redhat Linux 6 (RHEL 6) and Redhat Linux 7 (RHEL 7) servers.

## Requirements

None.

## Role Variables

Set the timezone for your server:
    ntp_timezone: America/New_York


Set the [NTP Pool Area](http://support.ntp.org/bin/view/Servers/NTPPoolServers) to use. Defaults to none, which uses the worldwide pool.

    ntp_servers:
      - "0{{ ntp_area }}.pool.ntp.org iburst"
      - "1{{ ntp_area }}.pool.ntp.org iburst"
      - "2{{ ntp_area }}.pool.ntp.org iburst"
      - "3{{ ntp_area }}.pool.ntp.org iburst"

## NTP Servers

   "AREA                       HOSTNAME"
  " ----                       --------"
   "Worldwide                  pool.ntp.org"
   "Asia                       asia.pool.ntp.org"
   "Europe                     europe.pool.ntp.org"
   "North America              north-america.pool.ntp.org"
   "Oceania                    aceania.pool.ntp.org"
   "South America              south-america.pool.ntp.org"


## Dependencies

None.

## Example Playbook

    - hosts: all
      roles:
        - role: ntp
          ntp_timezone: "{{ 'America/New_York' }}"
          ntp_area: "{{ 'north-america' }}"


## Author Information

This role was created in 2018 by [Michael Ventarola]
