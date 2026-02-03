# Install Netbox on Docker 

## Step 1 Setup Netbox
```bash
git clone https://github.com/mhdhaidarah/NetBox-Docker.git
cd NetBox-Docker
docker compose pull
```
## Step 2 Create Super User for Web GUI
```bash
docker compose exec netbox /opt/netbox/netbox/manage.py createsuperuser
```

## Step 3 Test and Browse
```bash
http://<Server-IP>:8000
```



