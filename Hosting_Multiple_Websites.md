## Hosting Multiple Websites

- we built already example.com dir in file: [link](nginx.conf.md)

# now we create same another website
- ```cd /usr/share/nginx/html/```
- ```sudo mkdir sample.com```
- ```cd sample.com```

# create index.html & style.css
- copy content from file: [index.html](sample.com/index.html) [style.css](sample.com/style.css)
- ```sudo vi index.html```
- ```sudo vi style.css```

# now we edit nginx.conf
- reference file: [link](nginx3.conf)
- ```sudo vi /etc/nginx/nginx.conf```
- ```sudo nginx -t```
- ```sudo systemctl reload nginx.service```