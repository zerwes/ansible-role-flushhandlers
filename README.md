# ansible-role-flushhandlers

ansible role to flush and execute pending handlers

as inbetween roles you can not insert tasks, we need a smal and simple role for the task

see:
 * https://github.com/zerwes/ansible-ensure-service-running
 * https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_handlers.html#controlling-when-handlers-run

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
