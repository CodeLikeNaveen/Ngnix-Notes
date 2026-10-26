## Changing the Default HTTP Port

- ```sudo vi /etc/nginx/nginx.conf```
- change port:
```nginx
        listen  8080;
```
- ```sudo systemctl reload nginx.service```

- it will not work if don't enable this port from AWS Security Group

## Adding this port
- Go to Instance → Security Groups → sg-xxxxxxxxxxxx
- Edit Inbound Rules
- Add rule
    - Custom Tcp
    - Port Range: 8080
    - Source-type: Anywhere-IPv4