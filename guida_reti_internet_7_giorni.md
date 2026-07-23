# Guida Pratica alle Reti e a Internet — Percorso in 7 Giorni

> Obiettivo: capire davvero come funziona Internet, saper usare il terminale per diagnosticare e analizzare reti, e avere le basi solide per proseguire verso la cybersecurity in modo etico e legale.

---

## Come usare questa guida

- Ogni giorno richiede **1-2 ore**.
- Ogni giorno ha: **Teoria** (concetti) + **Pratica** (comandi da terminale) + **Esercizio**.
- Usa un terminale Linux/macOS, oppure su Windows installa **WSL** (Windows Subsystem for Linux) o usa PowerShell/CMD dove indicato.
- Fai SEMPRE pratica solo sulla tua rete o su ambienti legali dedicati (te li indico al Giorno 7).

---

## GIORNO 1 — Cos'è Internet e come "viaggiano" i dati

### Teoria

Internet è una rete di reti: milioni di dispositivi collegati tra loro tramite protocolli condivisi. Per capirla, immagina la comunicazione a **livelli** (modello TCP/IP, versione semplificata del modello OSI):

1. **Applicazione** — il programma che usi (browser, email, ecc.) — protocolli: HTTP, HTTPS, DNS, FTP
2. **Trasporto** — divide i dati in pacchetti e garantisce (o no) l'affidabilità — protocolli: TCP (affidabile), UDP (veloce, non garantito)
3. **Rete** — instrada i pacchetti da un punto A a un punto B — protocollo: IP (Internet Protocol)
4. **Collegamento fisico** — il cavo, il Wi-Fi, la scheda di rete — Ethernet, Wi-Fi (802.11)

Ogni volta che apri un sito, i tuoi dati passano attraverso tutti questi livelli, vengono impacchettati, instradati attraverso router intermedi, e ricomposti a destinazione.

### Concetti chiave da memorizzare
- **IP address**: l'indirizzo univoco di un dispositivo in rete (es. 192.168.1.10)
- **MAC address**: l'indirizzo fisico della scheda di rete
- **Router**: instrada i pacchetti tra reti diverse
- **Switch**: collega dispositivi nella stessa rete locale
- **Pacchetto**: unità di dati trasmessa in rete

### Pratica da terminale

```bash
# Vedi il tuo indirizzo IP locale
ip addr show        # Linux
ifconfig             # macOS / Linux (vecchio stile)
ipconfig              # Windows (cmd)

# Vedi la tabella di routing
ip route              # Linux
route -n              # macOS

# Vedi il tuo IP pubblico
curl ifconfig.me
```

### Esercizio del giorno
Scopri il tuo IP locale, il tuo IP pubblico e la tua interfaccia di rete (es. `eth0`, `wlan0`). Scrivili su un foglio: ti serviranno nei prossimi giorni.

---

## GIORNO 2 — Indirizzi IP, Subnet e DNS

### Teoria

**Indirizzi IPv4**: 4 numeri da 0-255 separati da punti (es. `192.168.1.1`). Sono divisi in:
- **Rete privata** (usata in casa/uffici): `192.168.x.x`, `10.x.x.x`, `172.16.x.x - 172.31.x.x`
- **Rete pubblica**: tutto il resto, visibile su Internet

**Subnet mask** (es. `255.255.255.0` o `/24`): definisce quanti indirizzi appartengono alla stessa rete locale.

**DNS (Domain Name System)**: traduce nomi (`google.com`) in indirizzi IP (`142.250.180.14`), perché noi ricordiamo nomi, i computer usano numeri.

**DHCP**: il protocollo che assegna automaticamente un IP al tuo dispositivo quando ti connetti a una rete.

### Pratica da terminale

```bash
# Risolvere un dominio in IP
nslookup google.com
dig google.com          # più dettagliato (Linux/macOS)

# Vedere tutti i record DNS di un dominio
dig google.com ANY

# Risoluzione DNS inversa (da IP a nome)
nslookup 8.8.8.8

# Verificare la connettività DHCP
ip addr                 # controlla se hai un IP assegnato
```

### Esercizio del giorno
Usa `dig` o `nslookup` su 3 siti diversi (es. wikipedia.org, github.com, un sito a tua scelta) e annota i loro IP. Prova anche `dig +trace github.com` per vedere l'intero percorso di risoluzione DNS, dal root server fino al dominio finale.

---

## GIORNO 3 — Protocolli: come "parlano" i dispositivi

### Teoria

- **HTTP/HTTPS**: protocollo per navigare sul web. HTTPS = HTTP + cifratura (TLS/SSL).
- **TCP**: stabilisce una connessione affidabile (three-way handshake: SYN, SYN-ACK, ACK) prima di scambiare dati. Usato per web, email, file transfer.
- **UDP**: invia dati senza stabilire connessione, più veloce ma meno affidabile. Usato per streaming, gaming, DNS.
- **Porte**: ogni servizio su un computer "ascolta" su una porta specifica.
  - 80 = HTTP
  - 443 = HTTPS
  - 22 = SSH
  - 21 = FTP
  - 53 = DNS
  - 25 = SMTP (email)

### Pratica da terminale

```bash
# Vedere le connessioni di rete attive sul tuo PC
netstat -tulnp     # Linux (mostra porte in ascolto)
ss -tulnp          # alternativa moderna a netstat
lsof -i             # macOS/Linux, mostra processi collegati alla rete

# Testare se una porta è aperta su un host
curl -v telnet://google.com:443
nc -zv google.com 443    # netcat, verifica rapida porta

# Vedere l'header HTTP di un sito (senza scaricare la pagina)
curl -I https://www.wikipedia.org
```

### Esercizio del giorno
Usa `curl -I` su 5 siti diversi e osserva gli header di risposta (server usato, tipo di contenuto, cookie, ecc.). Prova poi `netstat`/`ss` sul tuo PC per vedere quali programmi hanno connessioni di rete aperte in questo momento.

---

## GIORNO 4 — Diagnostica di rete da terminale

### Teoria

Quando una connessione non funziona, un professionista IT segue un percorso logico di diagnosi: verifica il proprio dispositivo → il gateway locale → il DNS → la destinazione finale.

### Pratica da terminale (i comandi più importanti che userai per tutta la vita)

```bash
# PING: verifica se un host è raggiungibile e misura la latenza
ping -c 4 google.com

# TRACEROUTE: mostra tutti i "salti" (router) che i pacchetti attraversano
traceroute google.com   # Linux/macOS
tracert google.com      # Windows

# MTR: combina ping + traceroute in tempo reale (se installato)
mtr google.com

# Verifica velocità di connessione
curl -o /dev/null -s -w "Tempo totale: %{time_total}s\n" https://www.google.com

# Vedi tutti i dispositivi sulla tua rete locale (richiede nmap)
nmap -sn 192.168.1.0/24
```

### Esercizio del giorno
1. Fai un `traceroute` verso 2-3 siti diversi (uno vicino geograficamente, uno lontano) e confronta il numero di salti (hop) e la latenza.
2. Con `nmap -sn` scansiona la TUA rete di casa (solo la tua!) e prova a identificare tutti i dispositivi collegati (smart TV, telefono, router, ecc.).

⚠️ Nota importante: `nmap` va usato **solo** sulla tua rete o su reti per cui hai il permesso esplicito. Scansionare reti altrui senza autorizzazione è illegale in quasi tutti i paesi.

---

## GIORNO 5 — Sicurezza di rete: le basi

### Teoria

- **Firewall**: filtra il traffico in entrata/uscita in base a regole (porte, IP, protocolli).
- **VPN**: crea un tunnel cifrato tra il tuo dispositivo e un server remoto, nascondendo il traffico agli intermediari.
- **NAT**: permette a più dispositivi di una rete privata di condividere un solo IP pubblico.
- **TLS/SSL**: cifra le comunicazioni HTTPS, impedendo che terzi leggano i dati in transito.
- **Cifratura simmetrica vs asimmetrica**: simmetrica = stessa chiave per cifrare/decifrare (veloce); asimmetrica = coppia di chiavi pubblica/privata (usata per lo scambio iniziale in TLS, per SSH, per firme digitali).

### Pratica da terminale

```bash
# Vedere lo stato del firewall
sudo ufw status                 # Ubuntu/Debian
sudo firewall-cmd --list-all    # Fedora/CentOS

# Analizzare il certificato TLS di un sito
openssl s_client -connect google.com:443 -showcerts

# Generare una coppia di chiavi SSH (fondamentale per accesso remoto sicuro)
ssh-keygen -t ed25519 -C "tuo_commento"

# Connettersi in SSH a un server (esempio)
ssh utente@indirizzo_server
```

### Esercizio del giorno
Genera la tua prima coppia di chiavi SSH e leggi la differenza tra chiave pubblica (`.pub`) e privata. Se hai un Raspberry Pi, un VPS, o anche solo un secondo PC in casa, prova a fare una connessione SSH reale.

---

## GIORNO 6 — Analisi del traffico e laboratorio pratico

### Teoria

Per capire cosa succede "sotto il cofano" quando navighi, gli esperti di rete usano strumenti di **packet sniffing** — analizzano i pacchetti che entrano/escono dal proprio dispositivo. Questo è fondamentale sia per il networking che per la sicurezza.

### Strumenti da installare

- **Wireshark** (GUI, il più usato al mondo per analisi pacchetti) — https://www.wireshark.org
- **tcpdump** (versione da terminale, già presente su quasi tutti i Linux/macOS)

### Pratica da terminale

```bash
# Catturare pacchetti sulla tua interfaccia di rete (richiede sudo)
sudo tcpdump -i eth0 -c 20        # cattura 20 pacchetti
sudo tcpdump -i any port 443      # solo traffico HTTPS
sudo tcpdump -i any host google.com  # solo verso/da google.com

# Salvare la cattura per analizzarla dopo in Wireshark
sudo tcpdump -i any -w cattura.pcap
```

### Esercizio del giorno
1. Apri Wireshark, avvia una cattura sulla tua interfaccia di rete.
2. Apri il browser e visita un sito qualsiasi.
3. Ferma la cattura e osserva: DNS query, handshake TCP (SYN/SYN-ACK/ACK), handshake TLS, richieste HTTP.
Questo esercizio da solo ti farà capire più cose sulla rete di ore di teoria.

---

## GIORNO 7 — Verso la cybersecurity (in modo legale ed efficace)

### Teoria

Il passaggio da "conoscere le reti" a "cybersecurity/ethical hacking" è naturale, ma va fatto **dentro un percorso legale e strutturato**: la differenza tra un professionista di sicurezza informatica e un criminale informatico non è la tecnica, è l'autorizzazione. Le stesse tecniche usate senza permesso sono reati penali in tutto il mondo (in Italia: art. 615-ter c.p. e leggi collegate).

### Percorso consigliato, in ordine

1. **Certificazioni base** (ottime per fondamenta solide e riconosciute):
   - CompTIA Network+ (reti)
   - CompTIA Security+ (sicurezza)
2. **Piattaforme di pratica legale (Capture The Flag / Labs)**:
   - **TryHackMe** — percorsi guidati per principianti, molto didattico
   - **Hack The Box** — più avanzato, community enorme
   - **OverTheWire (Wargames)** — ottimo per imparare Linux/terminale mentre risolvi puzzle di sicurezza
   - **PortSwigger Web Security Academy** — gratuito, focalizzato su sicurezza web
3. **Certificazione intermedia/avanzata**: eJPT, poi OSCP (Offensive Security) quando avrai basi solide
4. **Bug bounty legali**: piattaforme come HackerOne o Bugcrowd, dove aziende autorizzano ricercatori a trovare vulnerabilità in cambio di ricompense — è hacking reale, ma legale e retribuito

### Perché questo percorso funziona
Ogni piattaforma sopra ti dà un ambiente **isolato e autorizzato** dove puoi applicare esattamente le tecniche che vuoi imparare (scansione, exploit, privilege escalation, ecc.) senza rischiare conseguenze legali e imparando da percorsi strutturati da veri professionisti.

### Esercizio del giorno
Crea un account gratuito su **TryHackMe** e completa il percorso "Pre Security" — è pensato esattamente per chi arriva dai fondamenti di rete come quelli di questa guida.

---

## Riepilogo comandi da terminale da ricordare

| Comando | A cosa serve |
|---|---|
| `ip addr` / `ifconfig` | Vedi il tuo IP locale |
| `curl ifconfig.me` | Vedi il tuo IP pubblico |
| `ping` | Verifica se un host è raggiungibile |
| `traceroute` / `tracert` | Vedi il percorso dei pacchetti |
| `nslookup` / `dig` | Risoluzione DNS |
| `netstat` / `ss` | Connessioni di rete attive |
| `curl -I` | Header HTTP di un sito |
| `nmap -sn` | Scopri dispositivi sulla tua rete |
| `openssl s_client` | Analizza certificati TLS |
| `ssh-keygen` / `ssh` | Chiavi e connessioni sicure |
| `tcpdump` | Cattura pacchetti di rete |

---

## Note finali

- Ripeti ogni giorno gli esercizi pratici: la teoria da sola non basta, la mano deve abituarsi al terminale.
- Dopo questa settimana avrai le basi per capire il 90% delle conversazioni tecniche su reti e sicurezza — il livello "esperto" vero arriva con mesi di pratica su lab reali (TryHackMe/HTB), non con una sola settimana, ma qui hai le fondamenta corrette e nell'ordine giusto.
- Usa sempre e solo le tue reti o ambienti autorizzati per esercitarti.
