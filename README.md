# Ansible Role: macos-power

An Ansible role that sets macOS settings related to power management to the desired values.

# Role Variables

Available variables are listed below, along with default values in minutes:

    computersleep: '30'
    displaysleep: '15'
    harddisksleep: '60'
    wakeonnetworkaccess: 'On'
    restartpowerfailure: 'On'
    restartfreeze: 'On'

# Example Playbook

```yml
    - hosts: ci_macs
      roles:
        - { role: macos-power, 
            macos_power_settings: [
              { cmd : displaysleep,         desired_value: 'after 15 minutes' },
              { cmd : computersleep,        desired_value: 'Never' },
              { cmd : harddisksleep,        desired_value: 'Never' },
              { cmd : wakeonnetworkaccess,  desired_value: 'On' },
              { cmd : restartfreeze,        desired_value: 'Off' }
            ]
          }
```
## License

Apache 2.0
