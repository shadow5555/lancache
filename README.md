# lancache
this is built using the monothlic work to self host your own network lan game caching server

this is assuming you already have docker and docker compose installed

NOTE this will take up alot of space quickly. Before you install this container please make sure where this stores the cache files has enough space. NOTE I used a nfs mount from my stroage server hosted on another server within network I did this by mounting a nfs share using fstab. Please lookup instructions how to do this

My nfs mount in my case is mounted to cache which has two folders inside /cache/data and cache/logs. Modify this to suit your needs


ALSO NOTE if you are using dns elsewhere like a pihole for instance you might need to change your upstream dns 


docker run \
  --restart unless-stopped \
  --name lancache \
  -v /cache/data:/data/cache \
  -v /cache/logs:/data/logs \
  -p 80:80 \
  -p 443:443 \
  lancachenet/monolithic:latest
  
  
