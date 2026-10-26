## Check the logs of Nginx

- ```cd /var/log/nginx```
- check file
    - ```sudo ls```
- check file updated status
    - ```sudo ls -ltr```
- To view file content
    - ```sudo less access.log```
    - ```sudo less error.log```

## Nginx logs can grow over time and consume disk space. The recommended solution is log rotation.