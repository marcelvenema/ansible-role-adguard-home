# role: AdGuard Home

<table style="border:0px; width:100%"><tr><td width=160px valign=top><img src="media/icon_adguardhome.png" alt="AdGuard Home icon" width=128 height=128></td>
<td>
Ansible role for installation, configuration, usage and management of AdGuard Home. AdGuard Home is a powerful network-wide ad blocker and privacy-protection DNS server for your entire home network.<br>
The UI is accessible after installation via `https://(servername/ip-address):8084`<br><br>Official website: `https://adguard.com`<br><br>
</td>
</tr></table>

Ansible role Adguard Home : [Design](docs/DESIGN.md)  |  [Examples](examples)  |  [Test](molecule)  |  [Issues]()  |<br>
Latest version:

# Actions:

<table style="border:0px; width:100%">
<tr><th>Deployment</th><th>Administration</th></tr>
<tr>
  <td valign=top>install<br>uninstall<br></td>
</tr></table>

## Deployment

action: **install**<br>
Installation of the latest AdGuard Home version.<br>
variables:<br>
<kbd>uninstall</kbd> (optional) : Uninstall existing AdGuard Home instance before installation.<br>

```
- name: Install Adguard Home
  hosts: localhost
  roles:
   - role: adguard-home
     vars:
       action : install
```


action: **uninstall**<br>
Uninstallation of AdGuard Home. Removal of configuration folder.<br>
variables:<br>
<kbd>keep_data</kbd> (optional) : Keep all Cockpit data during uninstallation.<br>

```
- name: Uninstall Adguard Home
  hosts: localhost
  roles:
   - role: adguard-home
     vars:
       action : uninstall
```

***

- **changelog**<br>
  Change log.
  See [changelog](CHANGELOG.md)

- **roadmap**<br>
  Vision and future developments.
  See [roadmap](ROADMAP.md)

***

## Preparations
(none).


## Dependencies
Dependencies are listed in the **requirements.yml** file.<br>
Use `ansible-galaxy install ./requirements.yml --force` for installation.<br>
If this role is used in other playbooks or Ansible projects, the URL of this role must be added to the `requirements.yml` file. Using the above command, the role will be placed in the correct folder structure.

## Installation and configuration
Installation via the action variable <kbd>install</kbd>. (Re-)configuration via the action variable <kbd>configure</kbd>.

When using this role in other playbooks or Ansible projects:
```
- name: Install and configure AdGuard Home
  hosts: localhost
  roles:
   - role: adguard-home
     vars:
       action : install
```


When used as a stand-alone Ansible project:
```
- name: Install and configure AdGuard Home
  hosts: localhost
  tasks:

    - name: Install and configure AdGuard Home
      ansible.builtin.include_tasks:
        file: tasks/install.yml
```

## Additional information
The UI is accessible via `https://<servername/ip>:8084`.

## License
MIT

## Author
Marcel Venema
