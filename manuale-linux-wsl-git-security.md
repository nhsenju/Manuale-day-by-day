# MANUALE OPERATIVO — Linux, WSL, Git, Networking & Cybersecurity Difensiva
### Guida pratica da tenere aperta mentre lavori (3 giorni per diventare operativo)

---

## 0. INTRODUZIONE MINIMAL

**Cos'è Linux (5 righe)**
Linux è un sistema operativo, come Windows o macOS, ma open source e basato su terminale. È lo standard per server, sviluppo software e cybersecurity. Tutto si controlla con comandi testuali invece che con il mouse. Non ha bisogno di licenza, è leggero, ed è ovunque nel mondo IT professionale. Se lavori con codice, reti o sicurezza, prima o poi lo usi.

**Cos'è WSL (5 righe)**
WSL (Windows Subsystem for Linux) è un Linux vero (Ubuntu) che gira dentro Windows, senza dual-boot o macchine virtuali pesanti. Hai il terminale Linux e allo stesso tempo puoi usare i tuoi programmi Windows (VS Code, browser, ecc.). File e cartelle Linux sono separati da quelli Windows, ma puoi accedere a entrambi. È il modo più veloce per imparare Linux restando su Windows.

**Regola principale: dove lavorare**
- Lavora **sempre dentro** `~` (home Linux, es. `/home/tuonome/progetti`)
- **Non lavorare mai** dentro `/mnt/c/...` (il tuo C: di Windows visto da Linux)
- Motivo: `/mnt/c` è lentissimo e rompe i permessi Linux. Usalo solo per prendere/spostare file occasionali.

> ✅ Regola d'oro: **home = lavoro**, **mnt/c = scambio file**

---

## 1. FILESYSTEM LINUX — solo le cartelle che userai davvero

| Cartella | A cosa serve | Quando la usi |
|---|---|---|
| `/` | Radice di tutto il sistema | Mai direttamente, ma tutto parte da qui |
| `/home` | Cartelle personali degli utenti | Qui vivi: `/home/tuonome` = la tua base |
| `/etc` | File di configurazione di sistema | Quando configuri servizi, rete, SSH |
| `/var` | Dati variabili: log, cache, servizi | Quando controlli i **log** (`/var/log`) |
| `/usr` | Programmi e librerie installate | Raramente a mano, gestito dai package manager |
| `/tmp` | File temporanei, si svuota al riavvio | Per test veloci, file usa-e-getta |
| `/mnt` | Punto di accesso ai dischi Windows (`/mnt/c`) | Solo per prendere file da Windows |
| `/proc` | Info live sul sistema (processi, CPU, RAM) | Diagnostica avanzata, raramente a mano |

---

## 2. COMANDI FONDAMENTALI

### 📍 Navigazione

| Comando | Spiegazione | Esempio |
|---|---|---|
| `pwd` | Mostra dove sei ora | `pwd` |
| `ls` | Lista i file nella cartella | `ls -la` (mostra tutto, anche nascosti) |
| `cd` | Cambia cartella | `cd progetti/sito-web` |

`cd ..` → sali di un livello · `cd ~` → torna alla home · `cd -` → torna alla cartella precedente

### 📁 File e cartelle

| Comando | Spiegazione | Esempio |
|---|---|---|
| `touch` | Crea un file vuoto | `touch script.py` |
| `mkdir` | Crea una cartella | `mkdir progetto-nuovo` |
| `cp` | Copia file/cartelle | `cp file.txt backup.txt` |
| `mv` | Sposta o rinomina | `mv vecchio.txt nuovo.txt` |
| `rm` | Elimina file | `rm file.txt` (⚠️ non c'è cestino) |
| `cat` | Mostra il contenuto di un file | `cat note.txt` |
| `nano` | Editor di testo da terminale | `nano note.txt` (salva: `Ctrl+O`, esci: `Ctrl+X`) |

`cp -r cartella/ dest/` e `rm -r cartella/` → aggiungi `-r` per lavorare su cartelle intere.

### 🔍 Ricerca

| Comando | Spiegazione | Esempio |
|---|---|---|
| `find` | Cerca file per nome/tipo | `find . -name "*.log"` |
| `grep` | Cerca testo dentro i file | `grep "errore" log.txt` |

Combinazione utile: `grep -r "TODO" .` → cerca "TODO" in tutti i file della cartella corrente.

### 🖥️ Sistema

| Comando | Spiegazione | Esempio |
|---|---|---|
| `whoami` | Chi sei (utente attivo) | `whoami` |
| `uname` | Info sul sistema | `uname -a` |
| `df` | Spazio disco disponibile | `df -h` (formato leggibile) |
| `top` | Processi attivi in tempo reale | `top` (esci con `q`) |
| `ps` | Elenco processi | `ps aux` |

### 🌐 Rete

| Comando | Spiegazione | Esempio |
|---|---|---|
| `ping` | Verifica se un host risponde | `ping google.com` |
| `ip` | Mostra config di rete | `ip a` |
| `ss` | Mostra connessioni/porte attive | `ss -tuln` |
| `curl` | Fa richieste web da terminale | `curl https://api.github.com` |
| `ssh` | Connessione remota sicura | `ssh utente@server` |

### 🔐 Permessi

| Comando | Spiegazione | Esempio |
|---|---|---|
| `chmod` | Cambia i permessi di un file | `chmod +x script.sh` (rende eseguibile) |

Permessi in breve: `r` = lettura, `w` = scrittura, `x` = esecuzione. `chmod 755 file` è lo standard per script condivisi.

---

## 3. GIT ESSENZIALE

| Comando | Spiegazione | Esempio |
|---|---|---|
| `git clone` | Scarica un repository | `git clone https://github.com/utente/repo.git` |
| `git status` | Vedi cosa è cambiato | `git status` |
| `git add` | Prepara i file per il commit | `git add .` (tutto) o `git add file.py` |
| `git commit` | Salva le modifiche con un messaggio | `git commit -m "fix bug login"` |
| `git push` | Invia le modifiche al remoto | `git push` |
| `git pull` | Scarica le modifiche più recenti | `git pull` |

### Workflow giornaliero completo

```bash
git pull                      # 1. aggiorna prima di iniziare
# ... lavori sui file ...
git status                    # 2. controlla cosa hai cambiato
git add .                     # 3. prepara i file
git commit -m "descrizione"   # 4. salva la modifica
git push                      # 5. invia al repository remoto
```

> 💡 Regola: `pull` prima di iniziare, `commit` spesso e piccoli, `push` a fine sessione.

---

## 4. WSL + VS CODE WORKFLOW

**Dove lavorare:** sempre dentro la home Linux, mai in `/mnt/c`.
```bash
cd ~
mkdir -p progetti/mio-progetto
cd progetti/mio-progetto
```

**Aprire il progetto in VS Code:**
```bash
code .
```
Questo apre VS Code direttamente collegato a WSL (vedrai "WSL: Ubuntu" in basso a sinistra). Da lì hai terminale integrato, estensioni, debug — tutto dentro Linux.

**Struttura progetto consigliata:**
```
mio-progetto/
├── src/          # codice sorgente
├── docs/         # documentazione
├── .gitignore    # file da escludere da git
└── README.md     # descrizione del progetto
```

---

## 5. NETWORKING BASE (security oriented)

| Comando | Cosa fa in pratica |
|---|---|
| `ip a` | Mostra le tue interfacce di rete e IP assegnati. Usalo per capire "che indirizzo IP ho ora". |
| `ss -tuln` | Mostra le porte aperte in ascolto sulla macchina. Usalo per capire "cosa sta esponendo servizi verso la rete". |
| `ping <host>` | Verifica se un host è raggiungibile. Primo comando da lanciare se "internet non va". |
| `curl <url>` | Fa una richiesta HTTP da terminale, utile per testare API o vedere se un sito risponde senza browser. |
| `ssh utente@host` | Apre una sessione remota cifrata su un altro computer/server. Base per amministrare macchine da remoto. |

**Lettura veloce di `ss -tuln`:**
- `t` = TCP, `u` = UDP, `l` = solo porte in ascolto, `n` = mostra numeri invece di nomi
- Una riga con `0.0.0.0:22` significa: porta 22 (SSH) aperta su tutte le interfacce.

---

## 6. CYBERSECURITY DIFENSIVA BASE (no offensive, solo difesa)

**Log di sistema (`/var/log`)**
I log registrano cosa succede sul sistema: accessi, errori, eventi. Sono la prima cosa da controllare quando sospetti un problema o un'anomalia.
```bash
cd /var/log
ls
cat syslog          # log generale di sistema
```

**Cercare errori/anomalie nei log**
```bash
grep -i "error" /var/log/syslog
grep -i "failed" /var/log/auth.log     # tentativi di accesso falliti
```

**Controllare processi e CPU sospetti**
```bash
top          # vedi in tempo reale cosa consuma risorse
ps aux       # lista completa dei processi attivi
```
Cosa cercare: processi sconosciuti, consumo CPU/RAM anomalo, processi lanciati da utenti inattesi.

**Utenti e permessi**
```bash
whoami                  # chi sei
cat /etc/passwd         # lista utenti del sistema
ls -la                  # vedi i permessi di file/cartelle (colonna rwx)
```
Principio di base: dai solo i permessi necessari (principio del minimo privilegio). Un file con `chmod 777` è quasi sempre un errore di sicurezza, non una soluzione.

---

## 7. WORKFLOW REALE QUOTIDIANO

```bash
# 1. Apri il terminale WSL (Ubuntu)

# 2. Vai al progetto
cd ~/progetti/mio-progetto

# 3. Aggiorna con l'ultima versione
git pull

# 4. Apri in VS Code
code .

# 5. Lavori sul codice/file (dentro VS Code o nano)

# 6. Controlli cosa hai cambiato
git status

# 7. Salvi le modifiche
git add .
git commit -m "descrizione modifica"

# 8. Invii tutto al repository
git push
```

---

## 8. CHEAT SHEET FINALE — tutto su una pagina

**Navigazione**
`pwd` `ls -la` `cd cartella` `cd ..` `cd ~`

**File**
`touch file` `mkdir cartella` `cp a b` `mv a b` `rm file` `cat file` `nano file`

**Ricerca**
`find . -name "*.txt"` `grep "testo" file` `grep -r "testo" .`

**Sistema**
`whoami` `uname -a` `df -h` `top` `ps aux`

**Rete**
`ping host` `ip a` `ss -tuln` `curl url` `ssh user@host`

**Permessi**
`chmod +x file` `chmod 755 file`

**Git**
`git clone url` → `git pull` → `git add .` → `git commit -m "msg"` → `git push` → `git status`

**WSL + VS Code**
`cd ~` (lavora sempre qui, MAI in `/mnt/c`) → `code .` (apre VS Code su WSL)

**Sicurezza difensiva**
`cd /var/log && cat syslog` · `grep -i "failed" /var/log/auth.log` · `top` / `ps aux` · `ls -la` (permessi)

---

*Stampa questa guida o tienila aperta in una scheda mentre lavori. In 3 giorni di pratica costante — ripetendo questi comandi ogni volta che apri il terminale — diventano automatici.*
