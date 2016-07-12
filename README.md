# Nginx Ansible Role

Installs and configures nginx.

# Configuration Options

Name                | Default               | Description
--------------------|-----------------------|------------------------------------------------
nginx_sites         | null                  | A list of site configurations
nginx_ssl_protocols | TLSv1 TLSv1.1 TLSv1.2 | Enables the specified protocols

# Usage example

```yaml
---
- hosts: all
  sudo: true
  roles:
    - role: nginx
      nginx_sites:
        - name: default
          ssl:
            certificate: /etc/letsencrypt/live/example.com/fullchain.pem
            certificate_key: /etc/letsencrypt/example.com/privkey.pem            
          locations:
            - proxy: http://127.0.0.1:8080
```

# License

[![GPLv3](http://www.gnu.org/graphics/gplv3-127x51.png)](http://www.gnu.org/licenses/gpl-3.0.html)

