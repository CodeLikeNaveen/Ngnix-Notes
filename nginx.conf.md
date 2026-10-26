## Structure of **nginx.conf** file

- actual file [Link](nginx.conf)

```nginx
user;

events{
}

http{
    server{
        location{}
    }
}
```

- Press Esc then q! for exit without save

## Remove current render files
- ```cd /usr/share/nginx/html```
- ```sudo rm -rf *```

## create a folder and simple index.html
- ```sudo mkdir example.com```
- ```cd example.com```
- ```sudo vi index.html```
    - create a basic html page and save exit
    - to check
        - ```cat index.html```
## create ngnix config from start
- ```cd /etc/nginx/```
- takes backup of original file
    - ```sudo cp nginx.conf nginx.conf_bcp```
- ```sudo rm nginx.conf```
- ```sudo vi nginx.conf```
- content in [file](nginx2.conf)
- test the syntex error:
- ```sudo nginx -t```

## reload the system
- ```sudo systemctl reload nginx.service```

## create a another page
- ```cd /usr/share/nginx/html/example.com/```
- ```sudo mkdir about```
- ```cd about```
- copy the home page index.html to this dir
    - ```sudo cp ../index.html .```
- ```sudo vi index.html```
- ```sudo systemctl reload nginx.service```


