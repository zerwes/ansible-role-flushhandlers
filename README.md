# ansible-role-flushhandlers
ansible role to flush and execute pending handlers 

see: https://github.com/zerwes/ansible-ensure-service-running

## howto

sample playbook

```yaml
- name: playday
  hosts: playground
  roles:
    - role: ansible-role-play
      tags:
        - play
    - role: flushhandlers
      tags: always
    - role: ansible-role-eat
      tags:
        - eat
    - role: flushhandlers  # sorry for the ambiguity :)
      tags: always
    - role: ansible-role-sleep
      tags:
        - sleep
```
