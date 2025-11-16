# ansible-role-freshrss

This role deploys [FreshRSS](https://www.freshrss.org/) to your server(s).

It **does not** deploy php, nor a webserver or a database. However, it does install the dependencies for FreshRSS, including php-sqlite3 in case you want to use a simple SQLite database.

## Example playbook

```yaml
- name: Deploy FreshRSS
  hosts: freshrss
  become: true

  roles:
    - freshrss
```

## Example var file

```yaml
freshrss_root_dir: "/var/www"
freshrss_path: "/var/www/rss"
freshrss_version: "1.27.1"
freshrss_refresh_interval: 15 # every 15 minutes
```

## FreshRSS configuration

It's done once deployed, navigate to the address you’ve installed your server to complete the installation from the GUI.

## License

This project is licensed under the GNU General Public License v3.0 or later (GPLv3+). See the [LICENSE](LICENSE) file for details.
