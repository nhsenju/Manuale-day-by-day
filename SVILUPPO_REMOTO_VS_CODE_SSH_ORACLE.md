# Sviluppo Remoto con VS Code, SSH e Oracle Cloud

## Obiettivo

Creare un ambiente di sviluppo professionale dove il computer locale viene usato solo come interfaccia, mentre il lavoro pesante viene eseguito su una macchina remota.

Il modello finale:

```
PC Windows
│
├── VS Code
├── Git
└── SSH Client
        │
        │ Connessione sicura SSH
        ↓
        
Oracle Cloud VM

├── Ubuntu Linux
├── Python
├── Node.js
├── Git
├── Progetti
├── Dipendenze
└── Servizi
```

---

# 1. Perché usare sviluppo remoto

## Approccio tradizionale

Sul PC locale:

```
Computer personale

├── IDE
├── Linguaggi
├── Librerie
├── Database
├── Docker
├── Progetti
└── Dipendenze
```

Problemi:

- consumo spazio disco
- rallentamento del sistema
- conflitti tra versioni
- difficoltà nel mantenere ambienti puliti

---

## Approccio remoto

Il computer locale diventa un terminale.

Il server remoto contiene:

- codice
- ambienti virtuali
- librerie
- database
- servizi

Vantaggi:

- PC più leggero
- ambienti separati
- sviluppo più vicino ai server reali
- maggiore portabilità

---

# 2. Oracle Cloud VM

Macchina utilizzata:

```
Sistema operativo:
Ubuntu Linux

CPU:
AMD EPYC 7742

RAM:
circa 1 GB

Disco:
45 GB
```

Utilizzo ideale:

- sviluppo web
- API
- automazioni
- piccoli servizi
- test

Non ideale per:

- grandi modelli AI
- database pesanti
- molti container contemporaneamente

---

# 3. Linux come ambiente di sviluppo

Il server utilizza Linux.

Comandi fondamentali:

## Posizione corrente

```bash
pwd
```

## Lista file

```bash
ls
```

## Entrare in una cartella

```bash
cd nome_cartella
```

## Creare cartelle

```bash
mkdir nome_cartella
```

## Copiare file

```bash
cp origine destinazione
```

## Spostare file

```bash
mv origine destinazione
```

---

# 4. SSH (Secure Shell)

SSH permette di controllare un computer remoto tramite una connessione sicura.

Schema:

```
Computer locale

       SSH

        ↓

Server remoto
```

Comando base:

```bash
ssh utente@indirizzo_ip
```

Esempio:

```bash
ssh ubuntu@IP_SERVER
```

---

# 5. Autenticazione SSH con chiavi

SSH utilizza una coppia di chiavi:

```
Chiave privata
        +
Chiave pubblica
```

## Chiave privata

Rimane sul computer personale.

Esempio:

```
ssh-key-2026-06-17.key
```

Non deve essere condivisa.

---

## Chiave pubblica

Viene inserita nel server.

Serve per verificare che il client possieda la chiave privata corretta.

---

## Connessione usando una chiave

```bash
ssh -i percorso_chiave utente@ip_server
```

Esempio:

```bash
ssh -i ~/.ssh/oracle-key ubuntu@123.xxx.xxx.xxx
```

---

# 6. VS Code Remote SSH

VS Code può lavorare direttamente su un server remoto.

Architettura:

```
VS Code Windows

        │

        │ SSH

        ↓

VS Code Server Linux
```

---

Quando viene effettuata la connessione:

1. VS Code apre una connessione SSH
2. verifica il sistema remoto
3. installa VS Code Server
4. crea un collegamento remoto
5. permette di lavorare sui file Linux

---

# 7. VS Code Server

Sul server viene installato:

```
~/.vscode-server
```

Serve per:

- modificare file remoti
- usare il terminale remoto
- installare estensioni
- fare debugging

Il codice non viene copiato sul PC.

Rimane sul server.

---

# 8. Struttura progetto consigliata

Sul server:

```
/home/ubuntu

├── projects
│
├── tools
│
└── configurazioni
```

I progetti vengono salvati:

```
/home/ubuntu/projects
```

---

# 9. Git Workflow

Git gestisce la versione del codice.

Workflow:

```
Scrittura codice

        ↓

git add

        ↓

git commit

        ↓

git push

        ↓

GitHub/GitLab
```

---

## Comandi principali

Creare repository:

```bash
git init
```

Aggiungere modifiche:

```bash
git add .
```

Creare commit:

```bash
git commit -m "descrizione modifica"
```

Inviare remoto:

```bash
git push
```

---

# 10. Python remoto

Gli ambienti Python vengono creati sul server.

Creazione ambiente:

```bash
python3 -m venv .venv
```

Attivazione:

```bash
source .venv/bin/activate
```

Vantaggi:

- niente librerie pesanti sul PC
- ogni progetto ha il proprio ambiente
- maggiore ordine

---

# 11. Node.js remoto

Node viene installato sul server.

Gestione consigliata:

```
NVM
```

Workflow:

```
NVM

 ↓

Node.js

 ↓

npm

 ↓

Applicazione
```

Permette di gestire più versioni di Node.

---

# 12. Docker

Docker crea ambienti isolati.

Concetto:

```
Applicazione

+

Dipendenze

+

Configurazione

=

Container
```

Esempio:

```
API Python

Docker Container


Database PostgreSQL

Docker Container
```

Vantaggi:

- ambienti riproducibili
- facile distribuzione
- separazione dei servizi

---

# 13. Workflow professionale completo

```
Idea progetto

        ↓

Repository GitHub/GitLab

        ↓

VS Code Remote SSH

        ↓

Oracle Cloud VM

        ↓

Sviluppo

        ↓

Test

        ↓

Git Commit

        ↓

Git Push

        ↓

Deploy
```

---

# 14. Tecnologie da imparare

## Linux

Da conoscere:

- filesystem
- permessi
- utenti
- processi
- servizi

Comandi importanti:

```bash
sudo
chmod
chown
systemctl
ps
top
```

---

## Git

Da imparare:

- branch
- merge
- rebase
- pull request
- tag

---

## Networking

Concetti:

- IP pubblico
- IP privato
- porte
- firewall
- DNS
- HTTP/HTTPS

Porte importanti:

```
22  SSH
80  HTTP
443 HTTPS
```

---

## Backend

Tecnologie:

- Python
- Node.js
- API REST
- Database SQL
- PostgreSQL

---

## DevOps

Tecnologie:

- Docker
- CI/CD
- GitLab CI
- GitHub Actions
- Nginx
- Terraform

---

# 15. Competenze acquisite

Durante questo percorso:

- gestione spazio Windows
- analisi filesystem
- uso WSL
- gestione server Linux
- creazione VM cloud
- connessione SSH
- gestione chiavi SSH
- VS Code Remote SSH
- modello client/server
- sviluppo remoto
- primi concetti DevOps

---

# Obiettivo finale

Il computer locale diventa:

```
VS Code
+
Browser
+
SSH
```

Il server remoto diventa:

```
Codice
+
Ambienti
+
Database
+
Servizi
+
Deploy
```

Questo modello permette di sviluppare in modo più vicino agli ambienti professionali.
