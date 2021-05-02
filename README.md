#### Dev environment:
1. Add the following domains to /etc/hosts that points to localhost.
```
dineshsonachalam@macbook ~ % cat /etc/hosts
127.0.0.1	localhost
127.0.0.1 mysql
127.0.0.1 api-adp.dineshsonachalam.com
127.0.0.1 api-search.dineshsonachalam.com
```
2. Generate self signed ssl certificate for localhost and paste in certs-dev folder.
```
openssl req -x509 -sha256 -nodes -newkey rsa:2048 -days 365 -keyout private.key -out certificate.crt
```

3. Start nginx server:
```
nginx -c /Users/dineshsonachalam/Desktop/ADP-Hackathon/nginx.conf -s reload

dineshsonachalam@macbook ~ % ps -ef | grep nginx
  501  3710     1   0  9:07PM ??         0:00.01 nginx: master process nginx -c /Users/dineshsonachalam/Desktop/ADP-Hackathon/nginx.conf
  501  3711  3710   0  9:07PM ??         0:00.00 nginx: worker process
  501  3712  3710   0  9:07PM ??         0:00.02 nginx: worker process
  501  3713  3710   0  9:07PM ??         0:00.02 nginx: worker process
  501  3714  3710   0  9:07PM ??         0:00.03 nginx: worker process
  501  4142  4110   0  9:26PM ttys002    0:00.01 grep nginx
```
4. Start the docker-compose
```
docker-compose up
```
