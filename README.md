# Octoprint Ansible

The goal of this project is to monitor a OctoPi server (OctoPi installation) and to not install it.
It uses Grafana Agent to export all Logs Octoprint, webcamd and HAProxy produces as well as all metrics.


## Services it monitors
- HAProxy
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

## TODOS
- [ ] Setup SSL for HAProxy

## License
MIT License

## Acknowledgment
This small Project is standing on the shoulder of giants, thank you all!
- [ansible-role-grafana_agent](https://github.com/nleiva/ansible-role-grafana_agent)