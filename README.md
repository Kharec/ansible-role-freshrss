# ansible-role-freshrss

This role deploys [FreshRSS](https://www.freshrss.org/) to your server(s).

It **does not** deploy php, nor a webserver or a database.

However, it does install the PHP dependencies for FreshRSS, including php-sqlite3 in case you want to use a simple SQLite database.

## Playbook example

```yaml
---
- name: Deploy FreshRSS
  hosts: freshrss_servers
  become: true
  vars:
    freshrss_root_dir: "/var/www"
    freshrss_version: "1.27.1"
    freshrss_refresh_interval: 15
  roles:
    - freshrss
```

## Variables:

| Variable                    | Default                            | Required | Description                                                      |
| --------------------------- | ---------------------------------- | -------- | ---------------------------------------------------------------- |
| `freshrss_root_dir`         | -                                  | **Yes**  | Directory where FreshRSS archive is downloaded and extracted     |
| `freshrss_path`             | `{{ freshrss_root_dir }}/freshrss` | No       | Web-accessible path where FreshRSS will be symlinked             |
| `freshrss_version`          | -                                  | **Yes**  | FreshRSS version to deploy (e.g., `"1.27.1"`)                    |
| `freshrss_refresh_interval` | -                                  | **Yes**  | Feed refresh interval in minutes (e.g., `15` = every 15 minutes) |

## FreshRSS configuration

The configuration is to be done once deployed.

Navigate to the address you’ve installed your server to complete the installation from the GUI.

## License

This project is licensed under the GNU General Public License v3.0 or later (GPLv3+). See the [LICENSE](LICENSE) file for details.
