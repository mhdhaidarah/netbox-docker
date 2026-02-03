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
# Optional
## Import Devices Library
```bash
sudo su
git clone https://github.com/netbox-community/Device-Type-Library-Import.git
cd Device-Type-Library-Import
python3 -m venv venv
source venv/bin/activate

pip install -r requirements.txt
cp .env.example .env
```

## Now Setup URL http://127.0.0.1 & Token the token can be generated from GUI users V1 Must Be
## EXAMPLE
```bash
NETBOX_URL=https://127.0.0.1
NETBOX_TOKEN=LE0GCreKBP0v3jbXauWLVqbmzKtH3BnhI1Z184TV
REPO_URL=https://github.com/netbox-community/devicetype-library.git
REPO_BRANCH=master
IGNORE_SSL_ERRORS=True
#REQUESTS_CA_BUNDLE=/etc/ssl/certs/ca-certificates.crt # you should enable this if you are running on a linux sys>
#SLUGS=c9300-48u isr4431 isr4331
```
## Update Here
```bash
sudo nano /opt/Device-Type-Library-Import/.env
```
## Install Device Library Importer
```bash
git clone https://github.com/netbox-community/devicetype-library.git ~/Device-Type-Library-Import/repo
```

## Select Vendors or download all
```bash
./nb-dt-import.py
```
## OR
```bash
./nb-dt-import.py --vendors mikrotik,ubiquiti
```




