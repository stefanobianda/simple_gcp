# Security

La VM e2-micro di GCP con le porte aperte nel firewall
Il container PostgreSQL in ascolto sull’IP pubblico

## External IP

✅ Verifica IP esterno della VM

Vai su GCP: Compute > VM instances

Trova la tua docker-vm e copia l’IP esterno. 

## Firewall Rule
🔥 Apri le porte nel firewall GCP

A. Vai su VPC Network and Firewall:
https://console.cloud.google.com/networking/firewalls

B. Crea una nuova regola firewall:

Campo   Valore

Nome    allow-postgres-redis

Target  Tutte le istanze nella rete (oppure selettivo su tag)

IP  0.0.0.0/0 (o il tuo IP fisso pubblico per più sicurezza)

Porte TCP   5432,6379

Azione  Consenti

Direzione   Ingress

## Connect with pgAdmin
🖥️ Connettersi da pgAdmin (dal Mac)

Nel tuo pgAdmin, crea una nuova connessione:


Campo   Valore

Host name/address   104.196.234.126

Port    5432

Username    stefano (come da .env)

Password    password da .env

DB name win

## Additional Security Remarks
🚨 Sicurezza (Importante!)

Esporre PostgreSQL e Redis direttamente su Internet non è raccomandato in produzione, ma per sviluppo/testing può andare.

Consigli:
Apri le porte solo al tuo IP (non 0.0.0.0/0)
Usa un firewall locale o iptables per limitare accesso
Oppure: configura un tunnel SSH se vuoi sicurezza senza esporre le porte
