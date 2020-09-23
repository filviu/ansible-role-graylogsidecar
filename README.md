Role Name
=========

Sets up Graylog Sidecar

Role Variables
--------------

> **graylog_server_url** url of Graylog server API  
> **graylog_server_api_token** API token for graylog

Check defaults/main for other variables that can be adjusted.

Example Playbook
----------------

    ---
    - name: Graylog Sidecar
      hosts: all
      become: yes
      
      roles:
        - role: silviuvulcan.graylogsidecar
          graylog_server_url: http://graylog.example.com:9000/api/
          graylog_server_api_token: xxx

License
-------

(BSD, MIT)


Author Information
------------------

https://github.com/silviuvulcan/ansible-role-graylogsidecar/
