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

# **Nginx Enable HTTPS**
- [fileLink](NginxEnableHTTPS.md)
- Go To [TLS Checker](https://www.cdn77.com/tls-test) to see how good your website

# **Reverse Proxy**
- [fileLink](ReverseProxy.md)

# **Nginx Load Balancing**
- [fileLink](Nginx_Load_Balancing.md)

# **Nginx Backup Server**
- Backup Server will only server in case of Primary Fail
- small change in code
```nginx
upstream backend {
    server 192.168.1.1:3000;
    server 192.168.1.2:3000;
    server 192.168.1.3:3000 backup;
}
```

# **Nginx caching**
- It is a process where Nginx stores copies of responses (like HTML, images, or API data) to serve them directly to users, reducing backend load and improving response times.

- do this to enable caching
```nginx
http{
    # Define cache path
    proxy_cache_path /var/cache/nginx levels=1:2 keys_zone=my_cache:10m inactive=60m max_size=1g;
    server{
        listen 80;
        server_name example.com;

        location /{
            proxy_cache my_cache;                   # Enable caching using the defined cache
            proxy_cache_valid 200 60m;              # Cache 200 OK responses for 60 minutes
            proxy_cache_key "$scheme$request_uri";  # Define the cache key

            proxy_pass http://backend_server;                 # Forward requests to the backend server
            add_header X-Cache-Status $upstream_cache_status; # Add cache status header for debugging
        }
    }
}
```