## Nginx
- It is a high-performance web server that delivers websites, handles requests, and
- can also work as a reverse proxy, load balancer, and caching tool to manage 
- scale web traffic efficiently.

## Launch an instance (EC2)
- Server Name
- Amazon Linux
- Key pair
- Allow HTTP traffic from the internet
- Launch Instance
- Connect → Connect

## Commands to run (for Amazon Linux)
- **Installing Nginx**
    - ```sudo yum install nginx -y```
- **Start Nginx service**
    - ```sudo systemctl start nginx```
    - check active or not
        - ```sudo systemctl status nginx```
    - other commands
        - ```sudo systemctl start/stop/reload nginx```
- **Copy Public IP**
    - paste in browser tab with http:// 
    - not with https://

## Ngnix config and a simple HTML web 
- **Nginx config**
    - ```cd /etc/nginx```
    - ```vi nginx.conf``` (view only mode)
- further work [fileLink](nginx.conf.md)

## Changing Default HTTP Port 80
- [fileLink](HTTP_Port_Change.md)

## Nginx Logging
- [fileLink](nginx_logs.md)


## Hosting Multiple Websites
- [fileLink](Hosting_Multiple_Websites.md)

## Custom Domain
- Register a domain name.
    - if want to try free domain [videoLink](https://www.youtube.com/watch?v=eu1BjND0gRo)
- After watching this video
- Go to Edit DNS &rarr; Host Records (A & AAAA)  &rarr; Edit
- Replace the IP with your AWS Instance Public IP
- Like my domain is: ramandeep.linkpc.net
- Test is as:
    - ```http://www.ramandeep.linkpc.net/```

## Configure Error Pages & Different logs handle
- [fileLink](Hosting_Multiple_Websites.md)
- If root path '/' file not found:
    - [fileLink](nginx5.conf)

## **Nginx Enable HTTPS**
- [fileLink]()