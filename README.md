# Syncthing

Ansible role that installs [Syncthing](https://syncthing.net) on Linux systems.

**NOTE:** Syncthing by default is configured to listen on 127.0.0.1:8384. If you wish to allow remote access, you must set the `syncthing_gui_address` variable to a different value, and then set the GUI username and password after installation.

## Requirements

* [community.general](https://docs.ansible.com/ansible/latest/collections/community/general/index.html) for the `community.general.xml` module.

## Role Variables

* `syncthing_repo`: When `true`, uses the Syncthing APT repo. Otherwise, it will use the distribution repo.
* `syncthing_user`: The user that Syncthing runs as.
* `syncthing_manage_user`: When true, the role manages the user account Syncthing runs as.
* `syncthing_service_state`: Sets the service state
* `syncthing_service_enabled`: Sets the service state on boot
* `syncthing_gui_address`: Address and port the GUI uses. Defaults to `127.0.0.1:8384`, can be changed to listen on all interfaces using `0.0.0.0:8384`.
* `syncthing_gui_user`: Username for the web GUI.
* `syncthing_gui_password`: Bcrypt hash of the password for the web GUI.
* `syncthing_gui_tls`: Enables or disables TLS on the web GUI. Defaults to false.
* `syncthing_usage_reporting`: Enables or disables anonymous usage reporting to the Syncthing developers.
* `syncthing_default_path`: Default path for folders. Defaults to the home directory of the syncthing user.

## Dependencies

None.

## Example Playbook

```yaml
- name: Syncthing
  hosts: all
  become: true
  roles:
    - cmurphy.syncthing
```

## License

MIT

## Author Information

Colin Murphy
