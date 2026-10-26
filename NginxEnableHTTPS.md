## Nginx Enable HTTPS
- HTTPS is a secure version of HTTP that encrypts data between your browser and a website, making it safe from hackers.
- It uses SSL/TLS to protect sensitive information like passwords and credit card details.

## run these command to get free certificates:
- ```sudo yum install certbot python3-certbot-nginx -y```

- First Stop the nginx
- ```sudo systemctl stop nginx```

- To generate certificates
- ```sudo certbot certonly --standalone -d ramandeep.linkpc.net```# yourdomain.com
- if demand provide the registred email address
 
## now we edit nginx.conf
- reference file: [link](nginx6.conf)
- ```sudo vi /etc/nginx/nginx.conf```
- ```sudo nginx -t```
- ```sudo systemctl start nginx.service```

## Add HTTPS port in Security Groups
- Go to Security Groups
- Edit inbounded rules
- Add HTTPS from anywhere
    