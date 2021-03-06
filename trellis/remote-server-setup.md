---
ID: 7765
post_title: Remote Server Setup
author: Ben Word
post_date: 2015-10-15 12:27:00
post_excerpt: ""
layout: doc
permalink: >
  https://roots.io/trellis/docs/remote-server-setup/
published: true
docs_project:
  - "19"
publish_to_discourse:
  - "0"
---
Setting up remote servers (staging/production) is similar to the [local development setup](https://roots.io/trellis/docs/local-development-setup/).

1. Configure your WordPress sites in `group_vars/<environment>/wordpress_sites.yml`. Also see the [Passwords docs](https://roots.io/trellis/docs/passwords/).
2. Add your server IP/hostnames to `hosts/<environment>`.
3. Specify public SSH keys for `users` in `group_vars/all/users.yml`. See the [SSH Keys docs](https://roots.io/trellis/docs/ssh-keys/).
4. Consider setting `sshd_permit_root_login: false` in `group_vars/all/security.yml`. See the [Security docs](https://roots.io/trellis/docs/security/).
5. Run `ansible-playbook -i hosts/<environment> server.yml`.