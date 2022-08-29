# Octoprint Ansible

![](https://img.shields.io/github/license/josuablejeru/octoprint-ansible)
![](https://img.shields.io/github/issues/josuablejeru/octoprint-ansible)
![](https://img.shields.io/github/downloads/josuablejeru/octoprint-ansible/total)
![](https://img.shields.io/github/sponsors/josuablejeru)

The goal of this project is to monitor and manage a OctoPi server (OctoPi installation) and to not install it.
It uses Grafana Agent to export all Logs Octoprint, webcamd and HAProxy produces as well as all metrics.

Plugins can be also installed by the corresponding Ansible Runbook `plugins.yml`.

Some changes are specific for Octoprint in combination with a Ender 3v2 which uses [Jyers/Marlin](https://github.com/Jyers/Marlin) Firmware.
[Here](https://github.com/Jyers/Marlin/wiki/OctoPrint-Settings#error-handling) are the extra changes made.

The OcotPi instance can be also remotly accessed by using tailscale, a Zero config VPN which works from anywhere, you can learn more about it on there [website](https://tailscale.com/)

## Services it monitors
- Octoprint
- webcamd

## Installation

## Usage
Working with ssh-keys

```bash
$ ssh-copy-id -i ~/.ssh/id_rsa.pub <YOUR_USER_NAME>@<IP_ADDRESS_OF_THE_SERVER>
```

Export following env vars befor interacting with ansible
```bash
export ANSIBLE_USER=<username>
export ANSIBLE_PASSWORD=<password>

export LOKI_USER=<user-id>
export PROMETHEUS_USER=<user-id>
export GRAFANA_API_KEY=<api-key>
export TAILSCALE_AUTHKEY=<auth-key>
```

## OctoPrint Plugins
Ansible can installes a list of Plugins sepcified in `templates/requirements.txt`.
Use the `plugins.yml` playbook to do so.

- TouchUI
- SimpleEmergencyStop
- NavbarTemp
- FloatingNavbar
- Themeify
- HeaterTimeout
- PrintTimeGenius
- BedLevelVisualizer
- ArcWelderPlugin
- FirmwareUpdater
- OctoPrint-Prometheus-Exporter
- OctoPrint-M73Progress
- OctoPrint-DetailedProgress
- OctoPrint-DisplayLayerProgress

## Access your Octopring Instance remotly

This Role uses Tailscale as a free, fast and secure method to access you Raspberry PI over a VPN.


Please visit the [documentation](https://tailscale.com/kb/1085/auth-keys/) to generate a Auth Key.

## License
MIT License

## Acknowledgment
This small Project is standing on the shoulder of giants, thank you all!
- [ansible-role-grafana_agent](https://github.com/nleiva/ansible-role-grafana_agent)
- [ansible-role-tailscale](https://github.com/artis3n/ansible-role-tailscale)
