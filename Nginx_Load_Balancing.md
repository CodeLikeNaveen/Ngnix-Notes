## Nginx Load Balancing
- Nginx load balancing is a feature where Nginx distributes incoming traffic across multiple
backend servers to ensure no single server gets overloaded, improving performance, reliability, and scalability of your application.

## Create another instance on EC2(like web-2)
- web-1 is created in [file](ReverseProxy.md)
- create same a web-2 server

- Edit the nginx.conf
```nginx
http{
    upstream backend_servers{
        server 13.53.212.xxx:80;
        server 13.53.166.xxx:80;
        server 13.51.212.xxx:80;
        server 13.54.166.xxx:80;
    }
    server{
        listen 80;
        server_name example.com;

        location /{
            proxy_pass http://backend_servers/;
        }
    }
}
```
- It uses's round round robin method like
- request goes to server(if 2 servers):
    - 1
    - 2
    - 1
    - 2

# **Different Modes of LB (Load Balancing)**

- **Round-Robin (Default)**: 
    - Evenly distributes requests across servers; no
configuration needed.

- **Least Connections**: 
    - Sends requests to the server with the fewest active
connections (least_conn).

- **IP Hash**: 
    - Routes requests based on the client's IP to ensure session
stickiness (ip_hash).

- **Weighted Round-Robin**: 
    - Assigns weights to servers to handle traffic
proportionally (server 127.0.0.1 weight=3;).