# Octoprint Ansible

The goal of this project is to monitor a OctoPi server (OctoPi installation) and to not install it.
It uses Grafana to export all Logs Octoprint, webcamd and Nginx produces as well as all metrics.


## Services it monitors
- NGINX
- Octoprint
- webcamd

## Installation

## Usage
Export following env vars befor interacting with ansible
```bash
export ANSIBLE_USER=<username>
export ANSIBLE_PASSWORD=<password>
export GRAFANA_API_KEY=<api-key>
```


## TODOS
- [ ] Setup SSL for Nginx

## License
MIT License

## Acknowledgment
This small Project is standing on the shoulder of giants, thank you all!
- [ansible-role-grafana_agent](https://github.com/nleiva/ansible-role-grafana_agent)