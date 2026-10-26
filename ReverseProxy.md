## ReverseProxy
- An Nginx reverse proxy acts as an intermediary between clients and backend servers.

- It forwards client requests to the appropriate server, handles responses, and provides benefits like load balancing, caching, and security.

## Create another instance on EC2 (like web-1)
- Allow anyone in Security Group (for few minutes to test)
- Check in your browser that everything works

- Edit the nginx.conf
```nginx
server{
    listen 8080;

    location /{
        proxy_pass http://13.53.212.xxx/;
    }
}
```
- Change the Security Group from allow anyone &rarr; to nginx's server's ip