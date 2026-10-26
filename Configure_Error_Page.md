## Configure Error Page
- create a html file like 404.html
- ```cd /usr/share/nginx/html/sample.com```
- ```sudo vi 404.html```
- copy and past the code from file: [Link](sample.com/404.html)

# now we edit nginx.conf
- reference file: [link](nginx4.conf)
- ```sudo vi /etc/nginx/nginx.conf```
- ```sudo nginx -t```
- ```sudo systemctl reload nginx.service```