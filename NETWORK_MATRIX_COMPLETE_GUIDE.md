# 🌐 NETWORK MATRIX COMPLETE GUIDE

## Da Zero a Network Expert

Versione: 1.0

Guida completa per capire:
- computer
- reti
- Internet
- server
- cloud
- sicurezza
- troubleshooting

---

# Indice

- 00 Mentalità Network Engineer
- 01 Fondamenti delle reti
- 02 Modello OSI
- 03 Modello TCP/IP
- 04 Pacchetti e comunicazione reale
- 05 Ethernet e MAC Address
- 06 Switch e Layer 2
- 07 Indirizzi IP
- 08 IPv4
- 09 IPv6
- 10 Subnetting
- 11 CIDR
- 12 ARP
- 13 DHCP
- 14 DNS
- 15 NAT
- 16 Routing
- 17 TCP
- 18 UDP
- 19 Porte e servizi
- 20 HTTP HTTPS TLS
- 21 Firewall
- 22 VPN
- 23 Linux Networking
- 24 Server Networking
- 25 Cloud Networking
- 26 Oracle Cloud Networking
- 27 Docker Networking
- 28 Kubernetes Networking
- 29 Sicurezza
- 30 Troubleshooting
- 31 Laboratori pratici
- 32 Percorso Network Engineer

---

# 00 - Mentalità Network Engineer

Un Network Engineer non vede una rete come un insieme di cavi.

Vede:



Dati
|
Pacchetti
|
Protocolli
|
Indirizzi
|
Percorsi
|
Dispositivi
|
Servizi


Ogni problema di rete è una domanda:



Dove si rompe la comunicazione?


---

# La rete è una catena

Quando apri un sito:



Browser
|
Sistema operativo
|
Scheda di rete
|
WiFi/Ethernet
|
Switch
|
Router
|
ISP
|
Internet
|
Firewall
|
Load Balancer
|
Server
|
Database
|
Applicazione


Ogni punto può creare un problema.

---

# Il modo corretto di ragionare

Mai chiedersi:

"Perché Internet non funziona?"

È troppo generico.

Un tecnico chiede:



Il dispositivo è acceso?

Ha un indirizzo IP?

Conosce il gateway?

Riesce a raggiungere altre reti?

Il DNS funziona?

La porta è aperta?

Il servizio risponde?


---

# Le tre domande fondamentali della rete

Ogni comunicazione necessita:

## 1. Identità

Chi sono?

Risposta:



MAC Address
IP Address
Hostname


---

## 2. Destinazione

Dove devo andare?

Risposta:



IP destinazione


---

## 3. Servizio

Chi deve ricevere il messaggio?

Risposta:



Porta


Esempio:



192.168.1.50:443


Significa:



Macchina:
192.168.1.50

Servizio:
HTTPS

Porta:
443


---

# 01 - Fondamenti delle reti

## Cos'è una rete?

Una rete è un gruppo di dispositivi che comunicano.

Esempio:



PC A
|
|
PC B


Questa è una rete.

Aggiungiamo uno switch:



PC A
|
|
Switch
|
|
PC B


Ora abbiamo una LAN.

---

# LAN

LAN significa:



Local Area Network


Una rete locale.

Esempi:

Casa:



Telefono
|
Computer
|
Router
|
Smart TV


Ufficio:



PC
|
Switch
|
Server


---

# WAN

WAN significa:



Wide Area Network


Una rete geografica.

Esempio:



Casa
|
ISP
|
Internet
|
Server remoto


---

# Internet

Internet non è un computer.

Internet è una rete di reti.

Schema:



Rete casa
|
|
ISP
|
|
Google
|
|
Cloud
|
|
Azienda


Tutte comunicano usando protocolli comuni.

---

# Protocollo

Un protocollo è una regola di comunicazione.

Come una lingua.

Esempi:

## HTTP

Per pagine web.



Client:
Dammi una pagina

Server:
Eccola


---

## DNS

Per trovare indirizzi.



Computer:
Qual è l'IP di google.com?

DNS:
142.x.x.x


---

## SSH

Per controllare server.



Computer locale
|
|
Server remoto


---

# Client e Server

## Client

Chi fa una richiesta.

Esempio:

Browser:



Voglio una pagina web


---

## Server

Chi risponde.

Esempio:

Web server:



Ecco la pagina richiesta


Schema:



CLIENT

|
|
v

SERVER


---

# Host

Un host è qualsiasi dispositivo in rete.

Esempi:



Computer
Server
Telefono
Router
Stampante
Cloud VM


Ogni host può avere:



Nome
IP
Servizi
Porte aperte


---

# Banda

La banda indica quanti dati possono passare.

Misura:



bit al secondo


Esempi:



Mbps
Gbps
Tbps


---

# Bit e Byte

Fondamentale:



8 bit = 1 Byte


Esempio:

Connessione:



100 Mbps


Diventa:



100 / 8

= 12.5 MB/s


---

# Latenza

La latenza è il tempo necessario per arrivare a destinazione.

Misura:



millisecondi


Esempio:



PC Milano

  |


Server Roma

10 ms


Internet veloce significa:

- molta banda
- poca latenza

---

# Throughput

È la velocità reale.

Esempio:

Connessione:



1 Gbps teorico


Reale:



700 Mbps


Quello è il throughput.

---

# Packet Switching

Internet funziona a pacchetti.

Un file:



VIDEO.mp4


diventa:



Pacchetto 1

Pacchetto 2

Pacchetto 3

Pacchetto 4


Ogni pacchetto viaggia nella rete.

Poi viene ricostruito.

---

# Circuit Switching

Vecchio sistema telefonico.

Creava una linea dedicata:


Telefono A

Telefono B


Internet usa invece:



Pacchetto 1
strada A

Pacchetto 2
strada B


---

# La rete come una città

Immagina:

## IP

È l'indirizzo.



Via Roma 10


---

## MAC

È il dispositivo specifico.



Persona dentro casa


---

## Porta

È la stanza.



Camera 443


---

## Switch

È il postino locale.

---

## Router

È il navigatore che sceglie la strada.

---

# FINE PARTE INIZIALE

# Prossimo capitolo:
# 02 - Modello OSI e TCP/IP

Argomenti:

- i 7 livelli della rete
- cosa succede dentro un pacchetto
- dove lavorano switch, router e firewall
- come analizzare un problema livello per livello

# 02 - Modello OSI e TCP/IP

Il modello OSI è uno dei concetti più importanti del networking.

Serve per capire:

- dove nasce un problema
- quale dispositivo lavora a quale livello
- come viaggiano i dati

Un Network Engineer ragiona quasi sempre seguendo i livelli.

---

# Il modello OSI

OSI significa:



Open Systems Interconnection


È formato da 7 livelli.

Dal più vicino all'utente:



7 Application
6 Presentation
5 Session
4 Transport
3 Network
2 Data Link
1 Physical


---

# Perché esistono i livelli?

Immagina una spedizione.

Non mandi una scatola direttamente.

Hai:



Contenuto
|
Imballaggio
|
Etichetta
|
Corriere locale
|
Centro spedizioni
|
Trasporto


La rete funziona allo stesso modo.

Ogni livello aggiunge informazioni.

Questo processo si chiama:



Encapsulation


---

# Encapsulation

Quando invii dati:

L'applicazione crea il messaggio.

Ogni livello aggiunge il proprio header.

Esempio:



DATI

HEADER TCP

HEADER IP

HEADER Ethernet


Alla fine diventa un pacchetto pronto per viaggiare.

---

# Quando arriva al destinatario

Succede il contrario.

Si chiama:



De-encapsulation


Vengono tolti gli header:



Ethernet
|
IP
|
TCP
|
Dati


---

# Layer 7 - Application

È il livello che vede l'utente.

Qui troviamo:



Browser
Email
Chat
Applicazioni


Protocolli:



HTTP
HTTPS
DNS
SMTP
FTP
SSH


---

## Esempio

Apri:



https://google.com


Il browser crea una richiesta:



GET /


Questa nasce nel Layer 7.

---

# Layer 6 - Presentation

Gestisce il formato dei dati.

Compiti:

## Crittografia

Esempio:



HTTPS
TLS
SSL


---

## Compressione

Esempio:



Ridurre dimensione file


---

## Conversione formato

Esempio:



JSON
UTF-8
XML


---

# Layer 5 - Session

Gestisce le sessioni.

Una sessione è una conversazione.

Esempio:



Client:

Apro comunicazione

Server:

Ok

Client:

Mantengo collegamento

Client:

Chiudo


---

# Layer 4 - Transport

È uno dei livelli più importanti.

Qui troviamo:



TCP
UDP


Si occupa di:

- porte
- affidabilità
- controllo errori
- ordine dei dati

---

# TCP

TCP significa:



Transmission Control Protocol


È affidabile.

Prima di comunicare crea una connessione.

---

# TCP Three Way Handshake

Quando un client si collega:

## Passo 1

Client:



SYN


"Voglio iniziare una comunicazione"

---

## Passo 2

Server:



SYN ACK


"Ho ricevuto la richiesta"

---

## Passo 3

Client:



ACK


"Perfetto, iniziamo"

---

Schema:



CLIENT SERVER

SYN ------------->

  <------------- SYN ACK


ACK ------------->

CONNESSIONE APERTA


---

# TCP garantisce

## Ordine

Se arrivano:



Pacchetto 3
Pacchetto 1
Pacchetto 2


TCP li rimette:



1
2
3


---

## Ritrasmissione

Se manca un pacchetto:



Pacchetto perso
|
|
v

TCP lo richiede nuovamente


---

## Controllo congestione

TCP evita di saturare la rete.

---

# UDP

UDP significa:



User Datagram Protocol


È più semplice.

Non crea connessione.

Invia direttamente.

---

Esempio:



Invio dati

Fine


---

Vantaggi:



Velocissimo
Bassa latenza


Svantaggi:



Nessuna garanzia
Nessun controllo ordine


---

Usato per:

- videogiochi
- streaming
- chiamate VoIP
- DNS

---

# Layer 3 - Network

Qui troviamo:



IP
Router
Routing


Questo livello decide:

"Dove deve andare il pacchetto?"

---

Esempio:



IP sorgente:

192.168.1.20

IP destinazione:

8.8.8.8


Il router guarda la destinazione.

---

# Layer 2 - Data Link

Qui troviamo:



Ethernet
MAC Address
Switch


Lavora nella rete locale.

---

Esempio:

Un computer vuole parlare con un altro nella stessa LAN.

Usa:



MAC Address


---

# Layer 1 - Physical

È il mondo fisico.

Comprende:



Cavi
Fibra ottica
WiFi
Segnali elettrici
Onde radio


Qui viaggiano:



0
1
0
1


---

# Tabella riassuntiva OSI

| Livello | Nome | Esempi |
|-|-|-|
|7|Application|HTTP DNS SSH|
|6|Presentation|TLS JSON|
|5|Session|Sessioni|
|4|Transport|TCP UDP|
|3|Network|IP Router|
|2|Data Link|MAC Switch|
|1|Physical|Cavi WiFi|

---

# Dispositivi e livelli

## Hub

Lavora:



Layer 1


Ripete tutto.

Ormai quasi inutilizzato.

---

## Switch

Lavora:



Layer 2


Usa MAC Address.

---

## Router

Lavora:



Layer 3


Usa IP.

---

## Firewall

Può lavorare:



Layer 3
Layer 4
Layer 7


Controlla:

- IP
- porte
- applicazioni

---

# Modello TCP/IP

Nella pratica Internet usa il modello TCP/IP.

È più semplice.

Ha 4 livelli:



Application

Transport

Internet

Network Access


---

# Confronto OSI vs TCP/IP



OSI TCP/IP

Application
Presentation > Application

Session /

Transport > Transport

Network > Internet

Data Link
Physical > Network Access


---

# Esempio completo

Apri un sito:



https://example.com


Succede:

---

## Layer 7

Browser crea:



GET /


---

## Layer 6

TLS cifra:



Dati cifrati


---

## Layer 4

TCP crea:



Connessione porta 443


---

## Layer 3

IP aggiunge:



IP sorgente

IP destinazione


---

## Layer 2

Ethernet aggiunge:



MAC sorgente

MAC destinazione


---

## Layer 1

Trasforma tutto in:



Segnali elettrici


---

# Mentalità da Network Engineer

Quando hai un problema:

Non saltare livelli.

Segui:



Layer 1

Il cavo funziona?

Layer 2

Lo switch vede il dispositivo?

Layer 3

Gli IP sono corretti?

Layer 4

La porta è aperta?

Layer 7

L'applicazione funziona?


---

# Fine Capitolo 02

Prossimo capitolo:

# 03 - Pacchetti e comunicazione reale

Vedremo:

- cosa contiene veramente un pacchetto
- header
- frame
- segmenti
- datagrammi
- come vedere il traffico con Wireshark e tcpdump
- viaggio completo di un pacchetto dentro Internet

# 03 - Pacchetti e comunicazione reale

Un Network Engineer deve capire una cosa fondamentale:

> La rete non trasporta "informazioni". Trasporta pacchetti.

Ogni volta che navighi, mandi un messaggio, fai una chiamata o scarichi un file, tutto viene trasformato in piccoli blocchi di dati.

---

# Il viaggio di un dato

Immaginiamo di aprire:



https://example.com


L'utente pensa:



Voglio vedere un sito


La macchina invece fa:



Testo HTML
|
Segmento TCP
|
Pacchetto IP
|
Frame Ethernet
|
Segnale elettrico/radio


---

# Le unità dei dati nei livelli

Ogni livello OSI dà un nome diverso ai dati.

| Livello | Nome del dato |
|-|-|
|7 Application|Data|
|6 Presentation|Data|
|5 Session|Data|
|4 Transport|Segmento TCP / Datagramma UDP|
|3 Network|Packet|
|2 Data Link|Frame|
|1 Physical|Bit|

---

# Bit

Il livello più basso.

Un bit può essere:



0


oppure:



1


Tutto Internet alla fine è una sequenza enorme di:



010101010101010101


---

# Frame

Il frame appartiene al livello 2.

È il pacchetto dentro una rete locale.

Contiene:



+----------------------+
| MAC destinazione |
+----------------------+
| MAC sorgente |
+----------------------+
| Tipo protocollo |
+----------------------+
| Dati |
+----------------------+
| Controllo errore |
+----------------------+


---

# Packet

Il packet appartiene al livello 3.

Contiene gli indirizzi IP.

Esempio:



+----------------------+
| IP sorgente |
+----------------------+
| IP destinazione |
+----------------------+
| Protocollo |
+----------------------+
| Dati |
+----------------------+


---

# Segmento TCP

TCP aggiunge informazioni per controllare la comunicazione.

Esempio:



+----------------------+
| Porta sorgente |
+----------------------+
| Porta destinazione |
+----------------------+
| Numero sequenza |
+----------------------+
| ACK |
+----------------------+
| Dati |
+----------------------+


---

# Encapsulation completa

Quando invii un dato:



DATI APPLICAZIONE

    +


HEADER TCP

    +


HEADER IP

    +


HEADER ETHERNET

    +


BIT


Diventa:



010101010101010101


e viaggia nella rete.

---

# Ricezione

Il computer destinatario fa il processo inverso.

Riceve:



BIT


diventa:



FRAME


poi:



PACKET


poi:



SEGMENTO TCP


poi:



DATI APPLICAZIONE


---

# Header

Un header è una parte aggiunta davanti ai dati.

Serve a dire:

"Come deve essere trattato questo contenuto?"

Esempio:

Una lettera normale:



CONTENUTO


Una lettera reale:



DESTINATARIO
MITTENTE
INDIRIZZO
CONTENUTO


L'indirizzo è l'header.

---

# MAC Header

Il livello Ethernet aggiunge:



MAC sorgente

MAC destinazione


Serve nella rete locale.

Esempio:

Computer:



MAC:
AA:BB:CC:11:22:33


Router:



MAC:
FF:EE:DD:44:55:66


---

# IP Header

Il livello IP aggiunge:



IP sorgente

IP destinazione


Esempio:



192.168.1.20

  |


8.8.8.8


---

# TCP Header

TCP aggiunge:



Porta sorgente

Porta destinazione

Numero sequenza

Controlli


Esempio:

Browser:



Porta casuale:
53000


Server:



Porta:
443


Comunicazione:



192.168.1.20:53000

    |

    |


8.8.8.8:443


---

# Il viaggio reale di un pacchetto

Scenario:

Computer:



192.168.1.20


vuole raggiungere:



8.8.8.8


---

# Passo 1

Il computer controlla:

"8.8.8.8 è nella mia rete?"

La rete locale:



192.168.1.x


Risposta:



No


Serve il router.

---

# Passo 2

Il computer cerca il gateway.

Esempio:



Gateway:

192.168.1.1


---

# Passo 3

Serve il MAC del router.

Il computer usa ARP.

Chiede:



Chi possiede 192.168.1.1?


---

# Passo 4

Il router risponde:



Sono io.

MAC:
AA:BB:CC:DD


---

# Passo 5

Il computer crea il frame.

Dentro:



MAC destinazione:

Router


Dentro il pacchetto:



IP destinazione:

8.8.8.8


---

# Passo 6

Il router riceve.

Apre il frame.

Guarda:



IP destinazione


Decide:

"Dove devo mandarlo?"

---

# Passo 7

Il router crea un nuovo frame.

Perché?

Perché cambia la rete.

Importante:

Gli IP restano.

I MAC cambiano.

---

# Regola fondamentale

Durante il viaggio:

## IP

Rimane quasi sempre uguale.

Indica:



Da dove arriva
Dove deve arrivare


---

## MAC

Cambia ad ogni salto.

Indica:



Chi è il prossimo dispositivo locale


---

# Esempio con più router

Percorso:



PC

|

Router casa

|

Router ISP

|

Router Europa

|

Server


Ogni salto:

Cambia:



MAC


Rimane:



IP destinazione


---

# Hop

Ogni passaggio tra router è un hop.

Esempio:



Computer

Hop 1
Router casa

Hop 2
ISP

Hop 3
Provider internazionale

Hop 4
Server


---

# TTL

Ogni pacchetto IP possiede un TTL:



Time To Live


Serve per evitare loop infiniti.

Esempio:

Pacchetto:



TTL = 64


Ogni router:



TTL -1


Quando arriva a:



0


viene eliminato.

---

# Perché esiste TTL?

Immagina un errore:



Router A
|
Router B
|
Router C
|
Router A


Il pacchetto girerebbe per sempre.

TTL lo blocca.

---

# ICMP

ICMP è un protocollo di controllo.

Usato da:



ping


Esempio:

Ping:



Sono raggiungibile?


Risposta:



Sì, eccomi.


---

# Ping

Comando:

```bash
ping google.com


Invia:

ICMP Echo Request


Riceve:

ICMP Echo Reply


Misura:

raggiungibilità
latenza
Traceroute

Mostra il percorso.

Comando:

Linux:

traceroute google.com


Windows:

tracert google.com


Esempio:

1  Router casa

2  ISP

3  Provider

4  Google

Analizzare pacchetti

Strumenti professionali:

tcpdump

Terminale.

Esempio:

tcpdump -i eth0


Mostra traffico.

Wireshark

Interfaccia grafica.

Permette di vedere:

pacchetti
protocolli
header
errori
Esempio Wireshark

Filtro:

tcp.port == 443


Mostra solo HTTPS.

Filtro:

dns


Mostra richieste DNS.

Filtro:

ip.addr == 192.168.1.10


Mostra traffico di un dispositivo.

Come ragiona un esperto

Davanti a un problema:

"Il sito non funziona"

Non pensa:

"Internet è rotto"

Pensa:

Layer 1?
Cavo/WiFi?

Layer 2?
MAC?

Layer 3?
IP?

Layer 4?
Porta?

Layer 7?
Applicazione?

Concetto chiave

Ogni comunicazione è:

Dati

+

Identità

+

Destinazione

+

Regole

+

Percorso


Capire questo significa iniziare a vedere la rete dall'interno.

Fine Capitolo 03

Prossimo capitolo:

04 - Ethernet e MAC Address

Argomenti:

come comunicano i dispositivi nella LAN
perché esiste il MAC Address
ARP
broadcast
unicast
multicast
collision domain
switch internamente

# 04 - Ethernet e MAC Address

Ethernet è una delle tecnologie più importanti della storia delle reti.

È il linguaggio principale usato nelle reti locali (LAN).

Quando colleghi:

- computer
- server
- stampanti
- router
- access point

nella maggior parte dei casi stai usando Ethernet.

---

# Cos'è Ethernet?

Ethernet definisce:

- come vengono creati i frame
- come vengono identificati i dispositivi
- come vengono trasmessi i dati nella rete locale

Lavora principalmente al:



Layer 2 - Data Link


Ricorda:



Layer 3 = IP
Layer 2 = MAC


---

# IP e MAC: differenza fondamentale

Molti confondono IP e MAC.

Sono completamente diversi.

---

# IP Address

Serve per comunicare tra reti diverse.

Esempio:



192.168.1.50


Risponde alla domanda:

> Dove si trova il dispositivo?

---

# MAC Address

Serve nella rete locale.

Esempio:



A4:5E:60:12:AB:90


Risponde alla domanda:

> Quale scheda di rete è questa?

---

# Analogia

Immagina una città.

IP:



Via Roma 10
Milano


MAC:



Nome della persona che vive lì


---

# Struttura MAC Address

Un MAC è lungo:



48 bit


Viene scritto:



XX:XX:XX:XX:XX:XX


Esempio:



00:1A:2B:3C:4D:5E


---

# Parti del MAC

Un MAC contiene informazioni sul produttore.

Esempio:



00:1A:2B


Identifica il produttore.

Esempio:

- Intel
- Cisco
- Apple
- Dell

---

# Scheda di rete (NIC)

Ogni dispositivo collegato ha una:


NIC

Network Interface Card


È il componente che permette la connessione.

Esempi:

- scheda Ethernet
- WiFi
- interfaccia virtuale cloud

---

# Esempio Linux

Per vedere le interfacce:

```bash
ip addr


Output esempio:

eth0

inet 192.168.1.20

link/ether
AA:BB:CC:DD:EE:FF
``` id="7y9d9k"

Abbiamo:

IP:



192.168.1.20


MAC:



AA:BB:CC:DD:EE:FF


---

# Frame Ethernet

Ethernet trasporta dati tramite frame.

Struttura:



+----------------------+
| MAC Destinazione |
+----------------------+
| MAC Sorgente |
+----------------------+
| Tipo Protocollo |
+----------------------+
| Dati |
+----------------------+
| Controllo errore |
+----------------------+


---

# MAC Destination

Indica:

"Chi deve ricevere questo frame?"

Esempio:



MAC destinazione:

AA:BB:CC:11:22:33


---

# MAC Source

Indica:

"Chi sta inviando?"

Esempio:



MAC sorgente:

FF:EE:DD:44:55:66


---

# EtherType

Dice quale protocollo è contenuto.

Esempi:

IPv4:



0x0800


IPv6:



0x86DD


ARP:



0x0806


---

# Comunicazione nella stessa LAN

Scenario:

Computer A:



IP:
192.168.1.10

MAC:
AA-AA-AA


vuole parlare con:

Computer B:



IP:
192.168.1.20

MAC:
BB-BB-BB


---

Il computer A conosce:



IP destinazione


ma non conosce:



MAC destinazione


Serve ARP.

---

# ARP

ARP significa:



Address Resolution Protocol


Serve per trovare:



IP → MAC


---

# Funzionamento ARP

Computer A:

"Chi possiede 192.168.1.20?"

Invia:



ARP Request


A tutta la rete.

---

Tutti ricevono:



Broadcast


Ma solo il proprietario risponde.

---

Computer B:

"Sono io"

Risponde:



ARP Reply

192.168.1.20 =
BB-BB-BB


---

Ora A può comunicare.

---

# ARP Cache

Il computer memorizza il risultato.

Comando Linux:

```bash
arp -a


oppure:

ip neigh


Esempio:

192.168.1.1

AA:BB:CC:DD:EE
``` id="7y8m3q"

Così non deve chiedere ogni volta.

---

# Broadcast

Broadcast significa:

"Invio a tutti"

Esempio:



Un computer parla

    |

    |


Tutti ricevono


MAC broadcast:



FF:FF:FF:FF:FF:FF


---

# Quando viene usato il broadcast?

Esempi:

## ARP

Cercare un MAC.

---

## DHCP

Cercare un server che assegni IP.

---

# Unicast

Comunicazione uno a uno.

Esempio:



PC A

|

|

PC B


È la comunicazione più comune.

---

# Multicast

Un mittente verso un gruppo.

Esempio:



Server streaming

    |


| | |

PC1 PC2 PC3


Usato per:

- streaming
- IPTV
- alcuni protocolli di rete

---

# Collision Domain

Prima degli switch:

Le reti Ethernet usavano hub.

Problema:

Due dispositivi trasmettono insieme.

Risultato:

Collisione.

---

Esempio:



PC A ----
HUB
PC B ----/


Se entrambi parlano:



BOOM
Collisione


---

# Switch moderno

Lo switch elimina quasi tutte le collisioni.

Perché?

Crea porte separate.



PC A
|
|
Porta 1

   SWITCH


Porta 2
|
|
PC B


---

# La tabella MAC dello switch

Uno switch impara automaticamente.

Esempio:

Riceve:



Frame da:

AA:AA:AA


Capisce:



AA:AA:AA
si trova sulla porta 1


Crea una tabella:



MAC Porta

AA:AA:AA 1

BB:BB:BB 2


---

# Come lavora uno switch

Riceve frame:



Destinazione:

BB:BB:BB


Controlla tabella.

Se conosce:

manda direttamente.

Se non conosce:

fa flooding.

---

# Flooding

Lo switch manda il frame a tutte le porte.

Tranne quella da cui è arrivato.

Serve per imparare.

---

# Full Duplex

Le reti moderne usano:



Full Duplex


Significa:

Ricevere e inviare contemporaneamente.

Esempio:



PC ---> Switch

PC <--- Switch


---

# Ethernet Speed

Evoluzione:



10 Mbps

100 Mbps

1 Gbps

10 Gbps

40 Gbps

100 Gbps


---

# Ethernet nei Cloud

Anche il cloud usa concetti simili.

Una macchina Oracle/AWS/Azure ha:



Interfaccia virtuale

MAC virtuale

IP privato

IP pubblico


La scheda fisica è nascosta.

---

# Concetto fondamentale

Quando due dispositivi nella stessa rete comunicano:

Il processo è:



IP destinazione

    |


Serve MAC

    |


ARP

    |


Frame Ethernet

    |


Switch

    |


Destinatario


---

# Regola da ricordare



MAC = comunicazione locale

IP = comunicazione tra reti


---

# Fine Capitolo 04

Prossimo capitolo:

# 05 - Switch e Layer 2 avanzato

Argomenti:

- come funziona uno switch internamente
- VLAN
- trunk
- access port
- STP
- broadcast domain
- reti aziendali reali

# 05 - Switch e Layer 2 avanzato

Lo switch è uno dei dispositivi più importanti nelle reti moderne.

Molte persone pensano:

"Lo switch collega semplicemente dei cavi."

In realtà uno switch è un piccolo computer specializzato che:

- analizza frame Ethernet
- impara indirizzi MAC
- decide dove inviare i dati
- separa reti
- evita loop
- crea segmentazioni

---

# Switch: il cuore della LAN

Una rete aziendale tipica:


         INTERNET

             |
             |

          ROUTER

             |
             |

          FIREWALL

             |
             |

          SWITCH

    /       |       \

  PC       Server    WiFi


Lo switch è il punto centrale della rete interna.

---

# Come funziona uno switch

Uno switch lavora principalmente al:



Layer 2 - Data Link


Utilizza:



MAC Address


Non guarda normalmente:



IP Address


---

# Il primo pacchetto di un dispositivo

Quando un computer si collega:

Lo switch non conosce ancora il dispositivo.

Esempio:



PC

MAC:
AA:AA:AA


Si collega alla porta 5.

Lo switch registra:



MAC Porta

AA:AA:AA 5


Questo processo si chiama:



MAC Learning


---

# MAC Address Table

Ogni switch possiede una tabella interna.

Esempio:



+----------------+---------+
| MAC Address | Porta |
+----------------+---------+
| AA:AA:AA | 1 |
| BB:BB:BB | 5 |
| CC:CC:CC | 8 |
+----------------+---------+


Questa tabella si chiama:



CAM Table


---

# Processo di forwarding

Scenario:

PC A vuole parlare con PC B.



PC A

MAC:
AA

    SWITCH


MAC:
BB

PC B


Lo switch riceve:



Destinazione:

BB


Cerca nella tabella.

Se trova:



BB = porta 8


Invia solo lì.

---

# Unknown Unicast

Cosa succede se lo switch non conosce il MAC?

Esempio:



MAC:
DD:DD:DD


La tabella non contiene DD.

Lo switch fa:



Flooding


Invia il frame:



a tutte le porte


---

# Aging della tabella MAC

Gli switch non tengono informazioni per sempre.

Dopo un periodo:



MAC vecchio
|
|
v

rimosso


Questo evita tabelle inutilmente piene.

---

# Broadcast Domain

Un broadcast è un messaggio per tutti.

Esempio:



PC

|

Broadcast

|

Tutti ricevono


Una rete con molti dispositivi può avere troppo traffico broadcast.

---

# Problema del broadcast

Immagina:



1000 computer


Un ARP diventa:



Un computer parla

    |


999 dispositivi ricevono


Questo crea rumore.

Soluzione:



VLAN


---

# VLAN

VLAN significa:



Virtual Local Area Network


Permette di creare reti separate dentro lo stesso switch.

---

Senza VLAN:


       SWITCH


PC1
PC2
PC3
PC4

Tutti insieme


---

Con VLAN:


       SWITCH


VLAN 10

PC1
PC2

VLAN 20

PC3
PC4


Sono reti logiche separate.

---

# Esempio aziendale

Un'azienda può avere:

## VLAN 10

Amministrazione:



192.168.10.x


---

## VLAN 20

Tecnici:



192.168.20.x


---

## VLAN 30

Server:



192.168.30.x


---

# Perché usare VLAN?

## Sicurezza

Gli utenti non sono tutti nella stessa rete.

---

## Organizzazione

Separi:

- uffici
- server
- telefoni
- WiFi ospiti

---

## Prestazioni

Riduci broadcast inutili.

---

# Access Port

Una porta access appartiene a una sola VLAN.

Esempio:



Porta 1

VLAN 10

PC amministrazione


Il computer non sa nulla delle VLAN.

---

# Trunk Port

Una porta trunk trasporta più VLAN.

Esempio:



Switch A

  |

  |


TRUNK

  |


Switch B


Può trasportare:



VLAN 10

VLAN 20

VLAN 30


---

# VLAN Tagging

Per distinguere le VLAN viene usato:



802.1Q


Aggiunge un tag al frame.

Esempio:

Prima:



Frame Ethernet


Dopo:



Frame Ethernet

VLAN ID


---

# Inter-VLAN Routing

Due VLAN diverse non comunicano direttamente.

Esempio:



VLAN 10

192.168.10.x

X

VLAN 20

192.168.20.x


Serve un router o Layer 3 Switch.

---

# Layer 3 Switch

Uno switch avanzato può fare anche routing.

Quindi:



Layer 2

Layer 3


Può:

- gestire VLAN
- creare gateway
- instradare traffico

---

# STP

STP significa:



Spanning Tree Protocol


Serve a evitare loop.

---

# Perché servono loop?

Le aziende vogliono ridondanza.

Esempio:


    Switch A

   /       \


Switch B ---- Switch C


Se un collegamento cade:

la rete continua.

Problema:

i frame possono girare all'infinito.

---

# Broadcast Storm

Un loop crea:



Frame infinito

Frame infinito

Frame infinito


Risultato:



Rete bloccata


---

# STP soluzione

STP crea un albero logico.

Blocca collegamenti inutili.

Esempio:

Prima:



A
|\
|
B--C


Dopo:



A
|
B
|
C


Se serve:

riattiva il collegamento.

---

# Root Bridge

STP sceglie uno switch principale.

Si chiama:



Root Bridge


Tutti i percorsi vengono calcolati rispetto a lui.

---

# Port Security

Gli switch possono limitare chi entra.

Esempio:

Porta ufficio:

Permesso:



Solo MAC del PC aziendale


Se cambia:



Blocco porta


---

# PoE

PoE significa:



Power over Ethernet


Permette di alimentare dispositivi tramite cavo Ethernet.

Esempi:

- telecamere IP
- telefoni VoIP
- access point WiFi

---

# Switch in Cloud

Nel cloud non tocchi fisicamente lo switch.

Ma esistono concetti simili:

- reti virtuali
- subnet
- security group
- virtual switch

Esempio:



VM

|

Virtual Switch

|

Cloud Network


---

# Diagnosi Layer 2

Problemi comuni:

## Nessun collegamento

Controllare:

```bash
ip link

MAC non visto

Controllare:

ip neigh

VLAN errata

Sintomo:

PC acceso

IP corretto

ma nessuna comunicazione
``` id="m9k4xz"

---

## Loop

Sintomo:



rete lentissima

CPU switch alta

molti broadcast


---

# Mentalità professionale

Quando un dispositivo non comunica nella LAN:

Controlla:



Cavo/WiFi

Porta switch

VLAN

MAC learning

ARP

IP

Routing


---

# Concetto chiave

Lo switch è il responsabile della comunicazione locale.

Ricorda:



Switch = MAC

Router = IP


---

# Fine Capitolo 05

Prossimo capitolo:

# 06 - Indirizzi IP: IPv4 da zero

Argomenti:

- struttura degli indirizzi IP
- binario
- ottetti
- classi storiche
- reti pubbliche e private
- gateway
- subnet mask
- come ragiona un router

# 06 - Indirizzi IP: IPv4 da zero

L'indirizzo IP è uno dei concetti fondamentali del networking.

Senza IP:



i dispositivi non saprebbero dove inviare i dati


L'IP è l'indirizzo logico di un dispositivo nella rete.

---

# Cos'è un indirizzo IP?

IP significa:



Internet Protocol


Un indirizzo IP identifica:



CHI sei nella rete

DOVE ti trovi

COME raggiungerti


Esempio:



192.168.1.50


---

# IPv4

IPv4 significa:



Internet Protocol version 4


È il sistema di indirizzamento più usato.

Un IPv4 è formato da:



32 bit


Divisi in:



4 gruppi da 8 bit


Chiamati:



ottetti


---

# Struttura IPv4

Esempio:



192.168.1.50


Diventa:



192 168 1 50

| | | |

8bit 8bit 8bit 8bit


Totale:



8+8+8+8

=

32 bit


---

# Il sistema binario

I computer ragionano in:



0
1


Ogni ottetto contiene 8 bit.

Esempio:



192


in binario:



11000000


---

# Valore degli 8 bit

Ogni posizione vale:



128 64 32 16 8 4 2 1


Esempio:



11000000


Calcolo:



128 + 64 + 0 + 0 + 0 + 0 + 0 + 0

=192


---

# Esempio completo

IP:



192.168.1.50


Binario:



11000000.10101000.00000001.00110010


---

# Range IPv4

Ogni ottetto va da:



0


a:



255


Perché:



8 bit

2^8

=256 valori


Quindi:



0-255


---

# Indirizzo IP composto da due parti

Un IP contiene:

## Network ID

La rete.

## Host ID

Il dispositivo.

Esempio:



192.168.1.50


Possibile divisione:



Rete:

192.168.1

Host:

50


---

# Subnet Mask

La subnet mask dice:

"Dove finisce la rete e dove iniziano gli host?"

Esempio:



255.255.255.0


---

# Come funziona la subnet mask

IP:



192.168.1.50


Mask:



255.255.255.0


Significa:



192.168.1

=
rete

50

=
host


---

# Scrittura CIDR

Invece di:



255.255.255.0


si usa:



/24


Quindi:



192.168.1.50/24


---

# Cosa significa /24?

Significa:



24 bit sono dedicati alla rete

8 bit agli host


Schema:



11111111.11111111.11111111.00000000


---

# Numero massimo host

Formula:



2^bit host - 2


Per /24:



8 bit host

2^8 = 256

256 - 2

=254 host utilizzabili


Perché togliamo:



Network address

Broadcast address


---

# Network Address

È il primo indirizzo.

Esempio:



192.168.1.0/24


Indica:



la rete intera


Non viene assegnato ai dispositivi.

---

# Broadcast Address

È l'ultimo indirizzo.

Esempio:



192.168.1.255


Serve per comunicare con tutti gli host.

---

# Esempio rete completa

Rete:



192.168.1.0/24


Abbiamo:

Network:



192.168.1.0


Primo host:



192.168.1.1


Ultimo host:



192.168.1.254


Broadcast:



192.168.1.255


---

# IP Pubblico

Un IP pubblico è visibile su Internet.

Esempio:



93.45.120.10


Usato per:

- server pubblici
- router Internet
- servizi cloud

---

# IP Privato

Gli IP privati vengono usati dentro reti locali.

Non sono direttamente raggiungibili da Internet.

Range:

---

## Classe A privata



10.0.0.0 - 10.255.255.255


---

## Classe B privata



172.16.0.0 - 172.31.255.255


---

## Classe C privata



192.168.0.0 - 192.168.255.255


---

# Esempio rete domestica

Internet:



IP pubblico

93.50.10.20


Router:



192.168.1.1


Computer:



192.168.1.10


Telefono:



192.168.1.20


---

# Gateway

Il gateway è la porta verso altre reti.

Esempio:

Computer:



192.168.1.10


Gateway:



192.168.1.1


Quando il computer vuole Internet:

manda tutto al gateway.

---

# Default Route

Il computer ha una regola:



Se conosco la destinazione:

invio direttamente

Se non la conosco:

manda al gateway


Questa regola è:



0.0.0.0/0


---

# Visualizzare IP Linux

Comando:

```bash
ip addr


Esempio:

eth0

inet 192.168.1.50/24
``` id="n6p3qx"

---

# Visualizzare routing

Comando:

```bash
ip route


Esempio:

default via 192.168.1.1
``` id="r8m5vz"

Significa:

Gateway:



192.168.1.1


---

# Configurazione statica

Un server spesso usa IP fisso.

Esempio:



Server Web

192.168.1.100


Perché?

Perché gli utenti devono sapere dove trovarlo.

---

# Configurazione dinamica

Un computer normale usa DHCP.

Esempio:

Accendi il PC.

Chiede:



Mi date un IP?


Il DHCP risponde:



Prendi:

192.168.1.50


---

# Loopback

Ogni computer ha:



127.0.0.1


Significa:



Io stesso


Test:

```bash
ping 127.0.0.1

APIPA

Se DHCP fallisce:

Windows assegna:

169.254.x.x
``` id="h5q8mv"

Significa:



Non ho ricevuto un IP valido


---

# Private vs Public

Schema:


             INTERNET

                |

          IP PUBBLICO

                |

              ROUTER

                |

      IP PRIVATI LOCALI


   PC     Server     Telefono


---

# Come ragiona un router

Riceve:



IP destinazione


Controlla:



Routing Table


Decide:



Quale strada usare


---

# Concetto fondamentale

Ricorda:



MAC:

Chi sei nella rete locale

IP:

Dove sei nella rete globale

Porta:

Quale servizio vuoi raggiungere


---

# Fine Capitolo 06

Prossimo capitolo:

# 07 - IPv6 e futuro dell'indirizzamento

Argomenti:

- perché IPv4 non basta più
- struttura IPv6
- indirizzi globali
- SLAAC
- differenze IPv4 vs IPv6
- perché il cloud usa sempre più IPv6

# 07 - IPv6 e il futuro dell'indirizzamento

IPv4 è stato il fondamento di Internet per decenni.

Il problema:



Il numero di indirizzi disponibili è limitato.


Con la crescita di:

- smartphone
- cloud
- IoT
- server
- dispositivi intelligenti

gli indirizzi IPv4 sono diventati insufficienti.

La soluzione è:



IPv6


---

# IPv4: il problema

IPv4 utilizza:



32 bit


Numero massimo:



2^32


Circa:



4,3 miliardi di indirizzi


Sembra enorme.

Ma Internet ha:

- miliardi di persone
- telefoni
- server
- sensori
- macchine virtuali

Gli indirizzi finiscono.

---

# IPv6

IPv6 significa:



Internet Protocol version 6


Utilizza:



128 bit


Numero di indirizzi:



2^128


Un numero gigantesco.

Circa:



340 undecilioni


Praticamente impossibile esaurirli.

---

# Differenza principale

IPv4:



192.168.1.50


IPv6:



2001:0db8:85a3:0000:0000:8a2e:0370:7334


IPv6 usa:



numeri esadecimali


---

# Sistema esadecimale

IPv6 usa base 16.

Simboli:



0-9

a-f


Esempio:



a = 10

b = 11

c = 12

d = 13

e = 14

f = 15


---

# Struttura IPv6

Un indirizzo IPv6:



128 bit


Diviso in:



8 gruppi da 16 bit


Esempio:



2001:0db8:0000:0000:0000:ff00:0042:8329


---

# Abbreviazione IPv6

IPv6 può essere scritto in forma corta.

Regola:

Gli zeri consecutivi possono essere sostituiti con:



::


Esempio:

Completo:



2001:0db8:0000:0000:0000:0000:0000:0001


Abbreviato:



2001:db8::1


---

# Parti di un IPv6

Un indirizzo IPv6 contiene:

## Network Prefix

Indica la rete.

---

## Interface ID

Indica il dispositivo.

Esempio:



2001:db8:1234:5678::10


Parte rete:



2001:db8:1234


Dispositivo:



::10


---

# CIDR IPv6

Anche IPv6 usa CIDR.

Esempio:



2001:db8::/64


Significa:



64 bit rete

64 bit dispositivo


---

# Tipi di indirizzi IPv6

IPv6 ha diversi tipi.

---

# Global Unicast

Indirizzo pubblico.

Paragonabile all'IP pubblico IPv4.

Esempio:



2001:db8::1


---

# Link Local

Presente automaticamente.

Inizia con:



fe80::


Serve per comunicare nella rete locale.

Esempio:



fe80::1234


---

# Loopback

Come IPv4:



127.0.0.1


IPv6:



::1


Significa:



Questo dispositivo


---

# Multicast

IPv6 usa molto il multicast.

Inizia con:



ff00::


Serve per inviare dati a gruppi.

---

# IPv6 e broadcast

Differenza importante:

IPv6 NON usa broadcast.

IPv4:



Invia a tutti


IPv6:

usa:



Multicast


---

# Perché eliminare il broadcast?

Il broadcast crea traffico inutile.

Esempio:

1000 dispositivi.

Un messaggio broadcast:



1 dispositivo invia

999 ricevono


IPv6 preferisce gruppi specifici.

---

# Configurazione IPv6 automatica

IPv6 può configurarsi automaticamente.

Metodo:



SLAAC


Significa:



Stateless Address Autoconfiguration


---

# Come funziona SLAAC

Un dispositivo:

1.

Si collega alla rete.

2.

Riceve informazioni dal router.

3.

Crea il proprio indirizzo IPv6.

Schema:



Router

|

Prefix IPv6

|

Computer crea indirizzo


---

# DHCPv6

IPv6 può usare anche DHCP.

Serve quando vuoi controllo centrale.

Esempio:

Azienda:



Server DHCPv6

   |

   |


Tutti i client


---

# Neighbor Discovery Protocol

IPv6 sostituisce ARP con:



NDP


Neighbor Discovery Protocol.

Fa:

- trovare dispositivi
- scoprire router
- risolvere indirizzi

---

# IPv4 vs IPv6

|Caratteristica|IPv4|IPv6|
|-|-|-|
|Bit|32|128|
|Formato|Decimale|Esadecimale|
|Broadcast|Si|No|
|ARP|Si|No NDP|
|Indirizzi|Limitati|Enormi|
|Configurazione|DHCP comune|SLAAC/DHCPv6|

---

# IPv4 e IPv6 insieme

Oggi Internet usa entrambi.

Questo sistema si chiama:



Dual Stack


Un dispositivo può avere:

IPv4:



192.168.1.20


IPv6:



2001:db8::20


---

# NAT e IPv6

IPv4 usa molto NAT perché mancano indirizzi.

Esempio:



100 dispositivi

   |


1 IP pubblico


IPv6 invece può dare:



Ogni dispositivo

un indirizzo pubblico unico


---

# Sicurezza IPv6

IPv6 è stato progettato con caratteristiche moderne.

Supporta:



IPsec


Che permette:

- autenticazione
- cifratura
- integrità dati

---

# IPv6 nel Cloud

I provider moderni supportano IPv6:

- macchine virtuali
- load balancer
- reti private
- servizi Internet

Schema:



Internet IPv6

  |


Cloud Router

  |


Subnet IPv6

  |


Virtual Machine


---

# Comandi Linux IPv6

Visualizzare indirizzi:

```bash
ip -6 addr


Routing IPv6:

ip -6 route


Ping IPv6:

ping6 google.com

Problemi comuni IPv6
IPv6 configurato ma senza routing

Sintomo:

indirizzo presente

ma Internet non funziona
``` id="k8v3mp"

---

## Firewall blocca IPv6

Molti configurano firewall IPv4 e dimenticano IPv6.

---

## DNS errato

Servono record:



A = IPv4

AAAA = IPv6


---

# Record DNS IPv6

Esempio:

IPv4:



example.com

A

93.10.20.30


IPv6:



example.com

AAAA

2001:db8::10


---

# Mentalità Network Engineer

IPv6 non è solo:

"più indirizzi"

È un cambio di modello.

Da:



pochi IP pubblici

NAT


a:



ogni dispositivo

con indirizzo globale


---

# Concetto chiave

Ricorda:



IPv4:

32 bit
NAT
Broadcast

IPv6:

128 bit
No NAT necessario
Multicast
Autoconfigurazione


---

# Fine Capitolo 07

Prossimo capitolo:

# 08 - Subnetting completo

Argomenti:

- capire veramente la subnet mask
- calcolare reti a mente
- /24 /25 /26 /27 /28
- network address
- broadcast
- numero host
- divisione reti aziendali
- metodo professionale del Network Engineer

# 08 - Subnetting completo

Il subnetting è uno degli argomenti che separa un semplice utilizzatore di rete da un vero Network Engineer.

Capire il subnetting significa capire:

- come dividere una rete
- quanti dispositivi può contenere
- dove finisce una rete e ne inizia un'altra
- come ragiona un router

---

# Cos'è il subnetting?

Subnetting significa:



Dividere una rete grande in reti più piccole


Esempio:

Una rete:



192.168.1.0/24


può essere divisa in:



192.168.1.0/26

192.168.1.64/26

192.168.1.128/26

192.168.1.192/26


---

# Perché esiste il subnetting?

Senza subnetting:



1000 computer

tutti nella stessa rete


Problemi:

- troppo broadcast
- poca sicurezza
- difficile gestione

---

Con subnetting:



Amministrazione

192.168.10.x

Tecnici

192.168.20.x

Server

192.168.30.x


---

# La subnet mask

La subnet mask separa:



NETWORK

HOST


Esempio:

IP:



192.168.1.50


Mask:



255.255.255.0


CIDR:



/24


---

# Significato di /24

/24 significa:



24 bit rete

8 bit host


In binario:



11111111.11111111.11111111.00000000


---

# Formula degli host

Formula:



2^bit host - 2


Perché -2?

Perché esistono:

## Network Address

Il primo indirizzo.

## Broadcast Address

L'ultimo indirizzo.

---

# Esempio /24

Rete:



192.168.1.0/24


Bit host:



8


Calcolo:



2^8 - 2

256 - 2

254 host


---

# Tabella subnet principali

|CIDR|Subnet Mask|Host disponibili|
|-|-|-|
|/24|255.255.255.0|254|
|/25|255.255.255.128|126|
|/26|255.255.255.192|62|
|/27|255.255.255.224|30|
|/28|255.255.255.240|14|
|/29|255.255.255.248|6|
|/30|255.255.255.252|2|

---

# Il concetto dei blocchi

Il subnetting funziona con blocchi.

Formula:



256 - subnet mask


Esempio:

/26:

Mask:



255.255.255.192


Calcolo:



256 - 192

=64


Il blocco è:



64


---

# Reti /26

Una /24 diventa quattro /26.

Rete originale:



192.168.1.0/24


Diventa:

---

## Prima subnet



192.168.1.0/26


Range:



192.168.1.1

fino a

192.168.1.62


Broadcast:



192.168.1.63


---

## Seconda subnet



192.168.1.64/26


Host:



192.168.1.65

192.168.1.126


Broadcast:



192.168.1.127


---

## Terza subnet



192.168.1.128/26


Host:



192.168.1.129

192.168.1.190


Broadcast:



192.168.1.191


---

## Quarta subnet



192.168.1.192/26


Host:



192.168.1.193

192.168.1.254


Broadcast:



192.168.1.255


---

# Metodo veloce del Network Engineer

Quando vedi:



192.168.50.10/27


Fai:

## Passo 1

Trova host:



32 - 27

=5 bit


---

## Passo 2

Calcola indirizzi:



2^5

=32


---

## Passo 3

Togli due:



30 host


---

## Passo 4

Trova blocco:

/27:

Mask:



255.255.255.224


Calcolo:



256-224

=32


Le reti aumentano di 32:



0

32

64

96

128

160

192

224


---

# Esempio completo

IP:



192.168.10.70/27


Mask:



255.255.255.224


Blocchi:



0
32
64
96
128


70 cade nel blocco:



64


Quindi:

Network:



192.168.10.64


Broadcast:



192.168.10.95


Host:



65-94


---

# VLSM

VLSM significa:



Variable Length Subnet Mask


Permette di creare subnet di dimensioni diverse.

Esempio azienda:

Server:



50 host


Ufficio:



20 host


Link router:



2 host


Non sprechi indirizzi.

---

# Esempio VLSM

Rete:



192.168.1.0/24


---

Server:

Serve 50 host.

Scelgo:



/26


Disponibili:



62


Uso:



192.168.1.0/26


---

Ufficio:

Serve 20 host.

Scelgo:



/27


Uso:



192.168.1.64/27


---

Router:

Serve 2 host.

Scelgo:



/30


Uso:



192.168.1.96/30


---

# Subnetting e sicurezza

Il subnetting aiuta a creare separazione.

Esempio:



VLAN Server

|

Firewall

|

VLAN Utenti


Gli utenti non accedono direttamente ai server.

---

# Subnetting nel Cloud

Nel cloud è fondamentale.

Esempio:

Virtual Network:



10.0.0.0/16


Divisa:



10.0.1.0/24

Web

10.0.2.0/24

Database

10.0.3.0/24

Management


---

# Errori comuni

## Errore 1

Confondere:



IP

con

Subnet


---

## Errore 2

Dimenticare:



Network

Broadcast


---

## Errore 3

Usare una subnet troppo grande.

Esempio:



1000 dispositivi

tutti /16


---

# Comandi utili Linux

Vedere configurazione:

```bash
ip addr


Calcolare subnet:

ipcalc 192.168.1.10/24


Routing:

ip route

Mentalità Network Engineer

Non pensare:

"Un IP è solo un numero."

Pensa:

IP

=

identità

+

rete

+

percorso
``` id="m4x7qp"

---

# Concetto chiave

Ricorda:



Subnetting significa controllo.

Controllo di:

spazio IP

broadcast

sicurezza

organizzazione


---

# Fine Capitolo 08

Prossimo capitolo:

# 09 - ARP e comunicazione locale

Argomenti:

- come IP trova MAC
- ARP Request
- ARP Reply
- ARP Cache
- Gratuitous ARP
- problemi ARP
- ARP spoofing e sicurezza

# 09 - ARP e comunicazione locale

ARP è uno dei protocolli più importanti nelle reti IPv4.

È il ponte tra:



Layer 3

IP Address

    |

    |


Layer 2

MAC Address


Senza ARP, in una rete Ethernet IPv4 i dispositivi non saprebbero a quale scheda inviare i frame.

---

# Il problema che risolve ARP

Immaginiamo:

Computer A:



IP:

192.168.1.10


vuole comunicare con:

Computer B:



IP:

192.168.1.20


Il computer A conosce:



IP destinazione


ma Ethernet richiede:



MAC destinazione


Problema:



192.168.1.20

chi è?


Serve ARP.

---

# Cos'è ARP?

ARP significa:



Address Resolution Protocol


Il suo compito:



Tradurre:

IP

↓

MAC


Esempio:



192.168.1.20

↓

AA:BB:CC:DD:EE:FF


---

# Dove lavora ARP?

ARP è un protocollo particolare.

Si trova tra:



Layer 2

e

Layer 3


Perché usa:

IP:



Layer 3


MAC:



Layer 2


---

# Comunicazione senza ARP

Senza ARP:



PC A

Conosce:

IP B

ma non conosce:

MAC B

↓

Impossibile creare frame Ethernet


---

# Processo ARP completo

Scenario:

PC A:



192.168.1.10

MAC:

AA-AA-AA


PC B:



192.168.1.20

MAC:

BB-BB-BB


---

# Passo 1: controllo cache

PC A controlla:



Ho già il MAC di 192.168.1.20?


Cerca nella:



ARP Cache


---

Se trova:



192.168.1.20

=

BB-BB-BB


usa direttamente il MAC.

---

Se non trova:

deve fare una richiesta.

---

# Passo 2: ARP Request

PC A invia:



ARP Request


Messaggio:



Chi possiede 192.168.1.20?

Risponda a 192.168.1.10


---

Questo messaggio viene inviato in:



Broadcast


MAC destinazione:



FF:FF:FF:FF:FF:FF


---

# Perché broadcast?

Perché PC A non sa chi possiede quell'IP.

Quindi chiede:



a tutti


---

# Passo 3: tutti ricevono

La rete riceve:



PC A

|

|


SWITCH

|


PC B
PC C
PC D


Tutti vedono il messaggio.

---

Ma solo:



192.168.1.20


risponde.

---

# Passo 4: ARP Reply

PC B risponde:



Sono io.

192.168.1.20

Il mio MAC è:

BB-BB-BB


---

Questa risposta normalmente è:



Unicast


cioè:



PC B

↓

PC A


---

# Passo 5: comunicazione normale

Ora PC A conosce:



IP:

192.168.1.20

MAC:

BB-BB-BB


Può creare:



Frame Ethernet


e inviare dati.

---

# ARP Cache

Ogni dispositivo conserva una tabella temporanea.

Esempio:



IP MAC

192.168.1.1 AA:11:22

192.168.1.20 BB:33:44


---

# Visualizzare ARP Cache Linux

Comando moderno:

```bash
ip neigh


Esempio:

192.168.1.1 dev eth0

lladdr AA:BB:CC:DD


Comando vecchio:

arp -a

Durata della cache

La cache ARP non è permanente.

Dopo un certo tempo:

vecchia informazione

↓

eliminata


Perché?

Perché un dispositivo potrebbe cambiare scheda di rete.

Esempio pratico

Prima:

192.168.1.20

MAC:

AA-AA-AA


Cambio scheda.

Dopo:

192.168.1.20

MAC:

BB-BB-BB


La vecchia informazione sarebbe sbagliata.

Gratuitous ARP

Un dispositivo può annunciare sé stesso.

Esempio:

Un server cambia IP.

Invia:

Sono io:

192.168.1.50

MAC:

XX-XX-XX


Questo è:

Gratuitous ARP

Perché usare Gratuitous ARP?

Serve per:

aggiornare cache
rilevare conflitti IP
sistemi HA (alta disponibilità)
Conflitto IP

Esempio:

Due dispositivi:

PC A:

192.168.1.50


PC B:

192.168.1.50


Problema:

La rete non sa chi è veramente.

Risultato:

connessioni instabili

pacchetti persi

ARP Spoofing

ARP non possiede autenticazione.

Un attaccante può dire:

Sono io il gateway


Esempio:

Router vero:

192.168.1.1

MAC:

AA-AA-AA


Attaccante:

192.168.1.1

MAC:

ZZ-ZZ-ZZ


La vittima aggiorna:

192.168.1.1

=

ZZ-ZZ-ZZ


Ora il traffico passa dall'attaccante.

Man in the Middle (MITM)

ARP spoofing può creare:

PC

 |

Attaccante

 |

Router

 |

Internet


L'attaccante può vedere o modificare traffico.

Difese contro ARP Spoofing
Dynamic ARP Inspection

Funzione degli switch gestiti.

Controlla:

IP

+

MAC

+

porta switch

DHCP Snooping

Lo switch impara:

quale IP appartiene a quale porta

Segmentazione VLAN

Riduce il dominio di attacco.

ARP in una rete con router

Caso importante.

PC:

192.168.1.10


vuole raggiungere:

8.8.8.8


Il PC NON cerca:

MAC di 8.8.8.8


Perché è fuori rete.

Cerca:

MAC del gateway


Esempio:

192.168.1.1

Questo concetto è fondamentale

Quando comunichi fuori dalla LAN:

IP destinazione:

server remoto


ma:

MAC destinazione:

router locale

Esempio completo

Computer:

IP:

192.168.1.50


Gateway:

192.168.1.1


Server Internet:

142.250.180.14


Frame:

MAC destinazione:

Router


Packet:

IP destinazione:

142.250.180.14

ARP e IPv6

IPv6 NON usa ARP.

Usa:

NDP

Neighbor Discovery Protocol


che lavora con:

ICMPv6

Diagnosi problemi ARP

Sintomi:

PC collegato

IP corretto

ma comunicazione impossibile


Controllare:

1

Vedere cache:

ip neigh

2

Pulire cache:

sudo ip neigh flush all

3

Catturare ARP:

sudo tcpdump -i eth0 arp

Wireshark filtro ARP

Filtro:

arp


Vedrai:

Who has 192.168.1.1?

Tell 192.168.1.50

Mentalità Network Engineer

Quando un PC non raggiunge un altro dispositivo nella stessa LAN:

ragiona:

1.

Ho un IP?


2.

Conosco il MAC?


3.

ARP funziona?


4.

Lo switch conosce il MAC?


5.

La VLAN è corretta?

Concetto chiave

ARP è il traduttore:

IP

↓

MAC


Il flusso reale:

Applicazione

↓

TCP/UDP

↓

IP

↓

ARP cerca MAC

↓

Ethernet Frame

↓

Switch

↓

Destinatario

Fine Capitolo 09

Prossimo capitolo:

10 - Routing: come Internet trova la strada

Argomenti:

cos'è un router
routing table
default gateway
static routing
dynamic routing
OSPF
BGP
come funziona Internet internamente

# 10 - Routing: come Internet trova la strada

Il routing è il cuore di Internet.

Se Ethernet permette ai dispositivi vicini di comunicare:



Layer 2

comunicazione locale


il routing permette di comunicare tra reti diverse:



Layer 3

rete A

↓

rete B

↓

rete C


---

# Cos'è il routing?

Routing significa:



scegliere il percorso migliore


Un router decide:



Dove mandare un pacchetto


usando:



Routing Table


---

# Router vs Switch

Differenza fondamentale:

## Switch

Lavora con:



MAC Address


Serve per:



stessa rete locale


---

## Router

Lavora con:



IP Address


Serve per:



collegare reti diverse


---

# Esempio semplice

Rete casa:



192.168.1.0/24


Internet:



8.8.8.8


Il computer pensa:



8.8.8.8 è nella mia rete?


Risposta:



No


Quindi:



Invio al router


---

# Default Gateway

Il gateway è il router che permette di uscire dalla rete.

Esempio:

PC:



192.168.1.50


Gateway:



192.168.1.1


Regola:



Destinazione sconosciuta

↓

Gateway


---

# Routing Table

Ogni dispositivo che fa routing possiede una tabella.

Esempio:



DESTINAZIONE VIA

192.168.1.0/24 locale

10.0.0.0/8 router A

0.0.0.0/0 Internet


---

# La regola più importante

Il router usa:



Longest Prefix Match


Significa:

sceglie la rotta più specifica.

---

# Esempio Longest Prefix

Routing table:



10.0.0.0/8

10.1.1.0/24


Pacchetto destinato a:



10.1.1.50


Entrambe corrispondono.

Il router sceglie:



10.1.1.0/24


Perché è più precisa.

---

# Il viaggio di un pacchetto

Computer:



192.168.1.20


vuole:



8.8.8.8


---

## Passo 1

Controlla subnet.



8.8.8.8

non è locale


---

## Passo 2

Cerca gateway:



192.168.1.1


---

## Passo 3

ARP:



Chi ha 192.168.1.1?


---

## Passo 4

Invia frame al router.

MAC:



Router


IP:



8.8.8.8


---

## Passo 5

Router riceve.

Guarda:



IP destinazione


---

## Passo 6

Consulta routing table.

---

## Passo 7

Invia al prossimo router.

---

# Hop

Ogni router attraversato è un:



Hop


Esempio:



PC

|

Router casa

|

ISP

|

Provider internazionale

|

Google


---

# TTL

Ogni pacchetto ha:



TTL

Time To Live


Ogni router diminuisce:



TTL -1


Serve a evitare loop.

---

# Routing statico

Una rotta inserita manualmente.

Esempio:



Rete:

10.10.0.0/16

via:

192.168.1.2


Vantaggi:

- semplice
- prevedibile

Svantaggi:

- difficile su grandi reti

---

# Esempio static route Linux

Aggiungere rotta:

```bash
sudo ip route add 10.10.0.0/16 via 192.168.1.2


Controllare:

ip route

Routing dinamico

Nelle grandi reti nessuno configura migliaia di rotte manualmente.

Usano protocolli dinamici.

Il router comunica con altri router.

Perché servono protocolli dinamici?

Immagina:

Internet

milioni di reti
``` id="z9m4qx"

Non puoi scrivere:



tutte le strade manualmente


Servono algoritmi.

---

# IGP e EGP

I protocolli di routing si dividono in:

---

# IGP

Interior Gateway Protocol.

Usati dentro una organizzazione.

Esempi:

- OSPF
- EIGRP
- RIP

---

# EGP

Exterior Gateway Protocol.

Usato tra organizzazioni diverse.

Il principale:



BGP


---

# RIP

Routing Information Protocol.

Vecchio protocollo.

Usa:



numero di hop


Esempio:



10 hop

meglio di

15 hop


Limite:

massimo 15 hop.

---

# OSPF

Open Shortest Path First.

Uno dei protocolli più usati nelle aziende.

Usa:



costo del percorso


Non guarda solo gli hop.

---

# Come ragiona OSPF

Ogni router conosce la rete.

Crea una mappa:



Router A

Router B

Router C


Poi calcola il percorso migliore.

---

# OSPF Areas

Per reti grandi:



Area 0

Area 1

Area 2


Area 0 è il backbone.

---

# BGP

BGP è il protocollo che muove Internet.

Internet è composta da:



Autonomous System


---

# Autonomous System

Un AS è una grande rete controllata da un'organizzazione.

Esempi:

- ISP
- Google
- Cloud provider

Ogni AS ha un numero:



ASN


---

# Come funziona BGP

BGP non cerca:



il percorso più veloce


Cerca:



la migliore politica di routing


Tiene conto di:

- accordi
- costi
- sicurezza
- preferenze

---

# Internet vista dall'alto

Schema:



Casa

|

ISP

|

Backbone Internet

|

Google

|

Cloud Provider


Ogni rete comunica tramite routing.

---

# NAT

Molte reti usano NAT.

Esempio:

Casa:



PC

192.168.1.10


Router:



IP pubblico

93.x.x.x


Il router traduce:



Privato

↓

Pubblico


---

# PAT

La forma più comune di NAT è:



PAT

Port Address Translation


Permette a molti dispositivi di condividere un IP pubblico.

---

Esempio:



PC1

192.168.1.10:5000

PC2

192.168.1.20:5001


Diventano:



IP pubblico

porte diverse


---

# Routing nei Cloud

Nel cloud il concetto è identico.

Esempio:

Virtual Network:



10.0.0.0/16


Subnet:



10.0.1.0/24

Web




10.0.2.0/24

Database


Router virtuali decidono il percorso.

---

# Comandi Linux routing

Visualizzare rotte:

```bash
ip route


Traceroute:

traceroute google.com


Test percorso:

tracepath google.com

Diagnosi professionale

Se un server non raggiunge Internet:

Controllare:

1.

IP corretto?


2.

Subnet corretta?


3.

Gateway presente?


4.

Routing table?


5.

Firewall?


6.

DNS?
``` id="m3v7qx"

---

# Mentalità Network Engineer

Un router non pensa:

"Invio dati"

Pensa:



Ho un pacchetto.

Qual è la destinazione?

Quale rete conosco?

Qual è il prossimo hop migliore?


---

# Concetto chiave

Ricorda:



Switch:

porta i dati nella LAN

Router:

porta i dati tra reti diverse

Routing:

sceglie la strada


---

# Fine Capitolo 10

Prossimo capitolo:

# 11 - TCP e UDP: il cuore delle comunicazioni

Argomenti:

- porte
- socket
- handshake TCP
- connessioni affidabili
- UDP
- differenze reali
- perché HTTPS usa TCP
- perché streaming e gaming usano UDP

# 11 - TCP e UDP: il cuore delle comunicazioni

Dopo aver capito:

- Ethernet
- MAC
- IP
- Routing

arriviamo al livello dove nasce la comunicazione tra applicazioni.

Il problema:

Un computer può avere migliaia di programmi aperti.

Esempio:



Browser

Email

Videogioco

SSH

Database


Tutti usano la rete contemporaneamente.

La domanda è:

> Come fa il computer a sapere quale programma deve ricevere i dati?

La risposta:



PORTA


---

# Le porte di rete

Una porta identifica un servizio.

Il numero della porta va da:



0

fino a

65535


Perché:



16 bit

2^16

=65536 valori


---

# IP + Porta

Un IP identifica:



il dispositivo


Una porta identifica:



il programma


Insieme formano:



Socket


Esempio:



192.168.1.50:443


Significa:



Computer:

192.168.1.50

Servizio:

porta 443 HTTPS


---

# Porte conosciute

Le prime porte sono standard.

## HTTP



80


Web non cifrato.

---

## HTTPS



443


Web cifrato.

---

## SSH



22


Accesso remoto Linux.

---

## FTP



21


Trasferimento file.

---

## DNS



53


Risoluzione nomi.

---

## SMTP



25


Invio email.

---

## MySQL



3306


Database.

---

# TCP

TCP significa:



Transmission Control Protocol


È un protocollo orientato alla connessione.

Significa:

Prima di scambiare dati:



crea una connessione


---

# Caratteristiche TCP

TCP offre:

## Affidabilità

Garantisce che i dati arrivino.

---

## Ordine

I dati arrivano nella sequenza corretta.

---

## Controllo errori

Rileva problemi.

---

## Controllo congestione

Evita di sovraccaricare la rete.

---

# Esempio reale

Scarichi un file:



100 MB


TCP divide:



Parte 1

Parte 2

Parte 3

Parte 4


Se manca:



Parte 3


TCP la richiede nuovamente.

---

# UDP

UDP significa:



User Datagram Protocol


È molto più semplice.

Non crea una connessione.

Invia direttamente.

---

# Caratteristiche UDP

UDP:

- veloce
- leggero
- senza garanzia
- senza controllo ordine

---

# Esempio UDP

Videochiamata.

Meglio:

Perdere un fotogramma.

Oppure:

Aspettare e creare ritardo?

La risposta:



Meglio velocità


---

# TCP vs UDP

|Caratteristica|TCP|UDP|
|-|-|-|
|Connessione|Si|No|
|Affidabilità|Alta|Bassa|
|Velocità|Media|Alta|
|Ordine dati|Garantito|No|
|Controllo errori|Si|Limitato|
|Uso tipico|Web, SSH, email|Gaming, streaming|

---

# Il modello TCP/IP

TCP lavora sopra IP.

Schema:



Applicazione

 |

TCP

 |

 IP

 |


Ethernet


---

UDP:



Applicazione

 |

UDP

 |

 IP

 |


Ethernet


---

# TCP Three Way Handshake

La caratteristica più famosa di TCP.

Prima di comunicare:

i dispositivi fanno una stretta di mano.

Si chiama:



Three Way Handshake


---

# Passo 1 - SYN

Client:



Ciao server.

Voglio aprire una connessione.


Invia:



SYN


---

# Passo 2 - SYN ACK

Server:



Ricevuto.

Accetto.


Risponde:



SYN + ACK


---

# Passo 3 - ACK

Client:



Perfetto.
Connessione pronta.


Invia:



ACK


---

Risultato:



Client

 |


TCP

 |


Server


Connessione stabilita.

---

# Esempio HTTPS

Apri:



https://google.com


Succede:

1.

DNS trova IP

2.

TCP handshake porta 443

3.

TLS handshake

4.

Scambio dati HTTPS

---

# TCP Sequence Number

TCP numera i dati.

Esempio:

Invio:



Pacchetto 1

Pacchetto 2

Pacchetto 3


Il ricevente controlla:



Ho ricevuto 1

Ho ricevuto 2

Manca 3


---

# ACK

ACK significa:



Acknowledgement


È una conferma.

Esempio:

Server:



Ho ricevuto fino al byte 5000


---

# Ritrasmissione

Se un pacchetto sparisce:

TCP aspetta.

Se non arriva conferma:



rimanda il dato


---

# Window Size

TCP controlla quanti dati può inviare senza aspettare.

Esempio:



Posso mandare 100 pacchetti


Questo migliora la velocità.

---

# Congestion Control

Internet non è infinita.

TCP deve capire:

"Quanto posso spingere?"

Se rileva problemi:

riduce velocità.

---

# Stati TCP

Una connessione TCP passa attraverso stati.

Esempio:



CLOSED

LISTEN

SYN SENT

ESTABLISHED

FIN WAIT

CLOSED


---

# Vedere connessioni TCP Linux

Comando:

```bash
ss -t


Tutte:

ss -tulnp


Esempio:

LISTEN

0.0.0.0:22


Significa:

SSH in ascolto.

Socket

Un socket è:

IP + Porta + Protocollo


Esempio:

192.168.1.10

porta 443

TCP

Client e Server

Server:

ascolta


Client:

inizia connessione


Esempio:

Web:

Server:

porta 443 LISTEN


Browser:

porta casuale

Porte effimere

Quando un client si connette:

non usa una porta fissa.

Esempio:

Browser:

192.168.1.50:52000


Server:

142.250.x.x:443

Comunicazione completa

Esempio HTTPS:

Client:

192.168.1.10:53000


↓

Internet

↓

Server:

142.250.x.x:443

UDP nel mondo reale

Usato per:

DNS

Piccole richieste veloci.

Gaming

Bassa latenza.

VoIP

Telefonia Internet.

Streaming live

Meglio velocità che perfezione.

TCP nel mondo reale

Usato per:

Web

HTTP/HTTPS.

SSH

Accesso remoto.

Email

SMTP, IMAP.

Database

Molti database usano TCP.

Perché HTTPS usa TCP?

Perché una pagina web deve arrivare corretta.

Se manca:

una parte HTML


la pagina può rompersi.

Serve:

affidabilità

Perché il gaming usa UDP?

In un gioco online:

Meglio:

posizione aggiornata subito


che:

posizione vecchia ma perfetta

Diagnosi TCP

Problema:

"Il sito non apre"

Controlli:

DNS
il nome diventa IP?

Ping
raggiungibile?

Porta
nc -vz server.com 443

Connessione TCP
ss

Firewall e TCP

Un firewall controlla:

IP

porta

protocollo


Esempio:

Permetti:

TCP 443


Blocca:

TCP 23

Concetto fondamentale

Ricorda:

IP:

Dove andare


Porta:

Quale servizio


TCP/UDP:

Come comunicare

Visione completa

Quando apri un sito:

Browser

↓

TCP porta 443

↓

IP server

↓

Router

↓

Internet

↓

Server Web

Fine Capitolo 11

Prossimo capitolo:

12 - DNS: il sistema nervoso di Internet

Argomenti:

come funzionano i nomi dominio
record A, AAAA, CNAME, MX
resolver
cache DNS
query ricorsive
DNS root server
troubleshooting DNS

# 12 - DNS: il sistema nervoso di Internet

DNS è uno dei servizi più importanti di tutta Internet.

Senza DNS il web esisterebbe ancora, ma sarebbe quasi inutilizzabile.

Dovremmo ricordare indirizzi come:



142.250.184.14


invece di:



google.com


---

# Cos'è DNS?

DNS significa:



Domain Name System


È il sistema che traduce:



NOME

↓

INDIRIZZO IP


Esempio:



www.example.com

↓

93.184.216.34


---

# Analogia semplice

DNS è come la rubrica del telefono.

Tu non ricordi:



+39 02 123456


Ricordi:



Mario


La rubrica fa:



Mario

↓

Numero telefono


DNS fa:



Dominio

↓

IP


---

# Perché esiste DNS?

I computer amano gli IP.

Gli esseri umani preferiscono nomi.

Computer:



142.250.185.46


Umano:



google.com


DNS crea il collegamento.

---

# Gerarchia DNS

DNS non è un unico server.

È una struttura gerarchica.

Schema:


            Root DNS

                |

         Top Level Domain

                |

         Authoritative DNS

                |

          Record DNS

                |

                IP


---

# Livello 1: Root Server

Sono i server DNS più alti nella gerarchia.

Esistono:



13 gruppi logici


ma fisicamente molti più server distribuiti nel mondo.

Conoscono:



dove trovare .com

dove trovare .it

dove trovare .org


---

# Livello 2: TLD

TLD significa:



Top Level Domain


Sono le estensioni:



.com

.org

.net

.it

.io


Esempio:

Per:



google.com


il root dice:



chiedi ai server .com


---

# Livello 3: Authoritative DNS

È il server che contiene la risposta finale.

Esempio:

Google possiede DNS autorevoli che dicono:



google.com

=

142.250.x.x


---

# Risoluzione DNS completa

Quando scrivi:



www.sito.com


succede:

---

## Passo 1

Il browser controlla cache locale.

Domanda:



Ho già questo IP?


---

## Passo 2

Se non lo trova:

chiede al resolver DNS.

Esempio:



8.8.8.8


oppure:



1.1.1.1


---

## Passo 3

Il resolver chiede al Root:



Chi gestisce .com?


---

## Passo 4

Root risponde:



Chiedi ai server .com


---

## Passo 5

Il resolver chiede:



Chi gestisce sito.com?


---

## Passo 6

Il DNS autorevole risponde:



sito.com

=

IP


---

## Passo 7

Il resolver restituisce:



IP al browser


---

# Schema completo



Browser

|

Resolver DNS

|

Root Server

|

TLD Server

|

Authoritative DNS

|

IP


---

# DNS Resolver

Il resolver è il server che fa il lavoro per il client.

Esempi:

Google:



8.8.8.8


Cloudflare:



1.1.1.1


ISP:



DNS del provider


---

# Record DNS

DNS non contiene solo IP.

Contiene diversi tipi di record.

---

# Record A

Collega:



Dominio

↓

IPv4


Esempio:



example.com

A

93.184.216.34


---

# Record AAAA

Collega:



Dominio

↓

IPv6


Esempio:



example.com

AAAA

2001:db8::10


---

# Record CNAME

Crea un alias.

Esempio:



www.sito.com

CNAME

sito.com


Significa:



www

è un altro nome per

sito.com


---

# Record MX

MX significa:



Mail Exchange


Indica il server email.

Esempio:



azienda.com

MX

mail.azienda.com


Quando arriva una mail:

DNS dice:



manda qui


---

# Record TXT

Contiene testo.

Usato per:

- verifiche dominio
- sicurezza email
- SPF
- DKIM

Esempio:



TXT

"v=spf1..."


---

# Record NS

Indica:



quali DNS sono autorevoli


Esempio:



example.com

NS

ns1.provider.com


---

# TTL DNS

TTL significa:



Time To Live


Indica quanto una risposta può essere memorizzata.

Esempio:



TTL:

3600 secondi


cioè:



1 ora


---

# Perché esiste la cache DNS?

Per velocizzare.

Senza cache:

Ogni visita farebbe:



Root

TLD

Authoritative


Ogni volta.

Troppo lento.

---

# Cache DNS

Esempio:

Prima visita:



DNS Query


Dopo:



IP già conosciuto


Risultato:

- più veloce
- meno traffico

---

# DNS e browser

Quando apri:



https://www.example.com


ordine:



1

DNS

↓

2

TCP 443

↓

3

TLS

↓

4

HTTPS


---

# DNS over HTTPS

Tradizionalmente DNS usa:



UDP 53


Problema:

le query possono essere osservate.

DNS over HTTPS:



DoH


invia DNS dentro HTTPS.

Porta:



443


---

# DNS over TLS

Alternativa:



DoT


usa:



TCP 853


---

# Attacchi DNS

DNS è fondamentale quindi viene attaccato.

---

# DNS Spoofing

Un attaccante modifica la risposta.

Esempio:

Tu chiedi:



banca.com


Risposta falsa:



vai a

server-attaccante.com


---

# DNS Cache Poisoning

Un attaccante inserisce dati falsi nella cache.

Risultato:

molti utenti ricevono risposte errate.

---

# DNSSEC

DNSSEC aggiunge firme digitali.

Serve per verificare:



questa risposta DNS è autentica?


---

# Diagnosi DNS

Problema:

"Internet non funziona"

Prima domanda:



È un problema DNS?


---

# nslookup

Comando:

```bash
nslookup google.com


Risultato:

Nome

↓

IP

dig

Strumento professionale Linux.

Esempio:

dig google.com


Mostra:

record
TTL
server risposta
Esempio dig

Output:

QUESTION SECTION

google.com A


ANSWER SECTION

google.com

142.250.x.x

Cambiare DNS Linux

Esempio:

Google DNS:

8.8.8.8


Cloudflare:

1.1.1.1

Test DNS

Test:

dig example.com


Controllare:

tempo risposta

server utilizzato

IP restituito

DNS in azienda

Le aziende spesso hanno:

DNS interno:

server.local


DNS esterno:

azienda.com

Split DNS

Stesso dominio.

Risposte diverse.

Esempio:

Dentro azienda:

server.azienda.com

10.0.0.5


Fuori:

server.azienda.com

IP pubblico

DNS nel Cloud

Nel cloud DNS è fondamentale.

Esempio:

Applicazione:

app.example.com


può puntare a:

Load Balancer


che punta a:

Server

Architettura moderna
Utente

 |

DNS

 |

Load Balancer

 |

Application Server

 |

Database

Mentalità Network Engineer

Quando un sito non funziona:

Non dire subito:

"Internet è giù"

Dividi:

1.

DNS risolve?


2.

IP raggiungibile?


3.

Porta aperta?


4.

Applicazione funziona?

Concetto chiave

Ricorda:

DNS:

trasforma nomi in indirizzi


IP:

porta il pacchetto alla macchina


TCP:

crea la comunicazione


HTTP:

trasporta il contenuto

Fine Capitolo 12

Prossimo capitolo:

13 - DHCP: come nasce un indirizzo IP

Argomenti:

DHCP Discover
DHCP Offer
DHCP Request
DHCP Ack
lease
reservation
DHCP server
DHCP relay
problemi reali di rete

# 13 - DHCP: come nasce un indirizzo IP

Ogni dispositivo collegato a una rete ha bisogno di una configurazione.

Per comunicare servono:



IP Address

Subnet Mask

Default Gateway

DNS Server


Configurare tutto manualmente su migliaia di dispositivi sarebbe impossibile.

La soluzione:



DHCP


---

# Cos'è DHCP?

DHCP significa:



Dynamic Host Configuration Protocol


È il protocollo che assegna automaticamente:

- indirizzo IP
- subnet mask
- gateway
- DNS
- durata della configurazione

---

# Esempio senza DHCP

Rete con 500 computer.

Ogni PC deve ricevere:



IP:

192.168.1.x

Mask:

255.255.255.0

Gateway:

192.168.1.1

DNS:

8.8.8.8


Configurazione manuale:

- lenta
- soggetta a errori
- difficile da mantenere

---

# Con DHCP

Il dispositivo entra nella rete.

Chiede:



Posso avere una configurazione?


Il server risponde:



Ecco il tuo IP.


---

# Componenti DHCP

Esistono:

## DHCP Client

Il dispositivo che chiede configurazione.

Esempio:

- PC
- smartphone
- server

---

## DHCP Server

Il dispositivo che assegna IP.

Può essere:

- router domestico
- server aziendale
- servizio cloud

---

# Porte DHCP

DHCP utilizza UDP.

Porte:

Client:



UDP 68


Server:



UDP 67


---

# Perché UDP?

Perché il client inizialmente non ha ancora un IP.

Non può creare una normale connessione TCP.

Serve qualcosa di semplice e veloce.

---

# Processo DHCP completo

Il processo classico è chiamato:



DORA


Significa:



D

Discover

O

Offer

R

Request

A

Ack


---

# 1 - DHCP Discover

Il client appena collegato non ha IP.

Invia:



DHCP Discover


Messaggio:



C'è qualche server DHCP disponibile?


---

Viene inviato in broadcast.

Perché?

Il client non conosce:

- il server
- il suo IP
- la rete completa

---

Esempio:



MAC Client:

AA:BB:CC:DD

IP:

0.0.0.0


Invia:



255.255.255.255


---

# 2 - DHCP Offer

Il server risponde:



Ti offro questo indirizzo:


Esempio:



IP:

192.168.1.50

Mask:

255.255.255.0

Gateway:

192.168.1.1

DNS:

8.8.8.8


---

# 3 - DHCP Request

Il client dice:



Accetto questa configurazione.


Invia:



DHCP Request


---

# 4 - DHCP ACK

Il server conferma:



Configurazione approvata.


Invia:



DHCP ACK


Ora il dispositivo può comunicare.

---

# Schema DORA



Client

|

DHCP Discover

|

Server

Server

|

DHCP Offer

|

Client

Client

|

DHCP Request

|

Server

Server

|

DHCP ACK

|

Client


---

# Lease DHCP

Un IP DHCP non è sempre permanente.

Si chiama:



Lease


cioè:



affitto dell'indirizzo


---

Esempio:

Server assegna:



192.168.1.50


per:



24 ore


Dopo deve essere rinnovato.

---

# Perché usare lease?

Immagina:

1000 telefoni.

Molti entrano ed escono.

Senza lease:



indirizzi bloccati inutilmente


---

# Rinnovo DHCP

Prima della scadenza il client dice:



Posso tenere questo IP?


Il server:



Sì.


---

# DHCP Reservation

A volte vuoi un IP fisso ma gestito da DHCP.

Esempio:

Server:



MAC:

AA:BB:CC:DD


Riceve sempre:



192.168.1.100


---

Usato per:

- stampanti
- server
- telecamere
- NAS

---

# IP Statico vs DHCP Reservation

## IP statico

Configurato direttamente sul dispositivo.

---

## Reservation

Gestito dal server DHCP.

Vantaggi:

- controllo centrale
- meno errori
- facile modifica

---

# Pool DHCP

Il server usa un intervallo.

Esempio:

Pool:



192.168.1.100

fino a

192.168.1.200


Può assegnare:



101 indirizzi


---

# Esclusioni DHCP

Alcuni IP non devono essere assegnati.

Esempio:

Router:



192.168.1.1


Server:



192.168.1.10


Stampante:



192.168.1.20


Questi vengono esclusi.

---

# DHCP Relay

Problema:

DHCP usa broadcast.

I router normalmente bloccano i broadcast.

---

Esempio:

VLAN 10:



PC


|

Router

|

VLAN 20:



DHCP Server


Il DHCP Discover non attraversa il router.

---

Soluzione:



DHCP Relay


---

# Come funziona DHCP Relay

Il router riceve:



DHCP Discover


e lo inoltra al server.

Schema:



Client

|

Router Relay

|

DHCP Server


---

# DHCP in azienda

Scenario:



1000 PC

50 VLAN

3 sedi


Serve:

- DHCP centralizzato
- relay
- prenotazioni
- logging

---

# DHCP Security

DHCP può essere attaccato.

---

# Rogue DHCP Server

Un attaccante collega un falso server DHCP.

Risultato:

Può assegnare:



Gateway falso

DNS falso


---

Esempio:

Utente riceve:



Gateway:

server-attaccante


Il traffico può essere intercettato.

---

# DHCP Snooping

Funzione degli switch gestiti.

Lo switch decide:



Questa porta può rispondere DHCP?


---

Esempio:

Porta router:



Trusted


Porta utente:



Untrusted


---

# DHCP e IPv6

IPv6 usa metodi diversi.

Può usare:

## SLAAC

Il dispositivo crea automaticamente l'indirizzo.

---

## DHCPv6

Server assegna configurazioni.

---

# Comandi Linux DHCP

Vedere IP:

```bash
ip addr


Vedere gateway:

ip route


Rinnovare DHCP:

sudo dhclient -r


poi:

sudo dhclient


Vedere informazioni DHCP:

journalctl | grep DHCP

Problemi comuni DHCP
Problema 1

PC riceve:

169.254.x.x


Significa:

DHCP fallito


Questo indirizzo si chiama:

APIPA

Problema 2

IP duplicato.

Cause:

statico sbagliato
DHCP configurato male
Problema 3

DHCP lento.

Possibili cause:

broadcast eccessivo
relay errato
server sovraccarico
Diagnosi professionale DHCP

Quando un PC non naviga:

Controllare:

1.

Ha ricevuto IP?


2.

Subnet corretta?


3.

Gateway presente?


4.

DNS presente?


5.

Lease valido?

Packet Capture DHCP

Con Wireshark filtro:

dhcp


Vedrai:

Discover

Offer

Request

ACK

Mentalità Network Engineer

Quando un dispositivo entra in rete:

non appare magicamente.

Succede:

Collegamento fisico

↓

DHCP

↓

IP

↓

Gateway

↓

DNS

↓

Comunicazione

Concetto chiave

Ricorda:

DHCP dà identità alla macchina.

ARP trova il vicino.

DNS trova i nomi.

Routing trova la strada.

Fine Capitolo 13

Prossimo capitolo:

14 - VLAN e Switching professionale

Argomenti:

come ragiona uno switch
VLAN 802.1Q
Access port
Trunk port
Native VLAN
VLAN tagging
Broadcast domain
Inter-VLAN routing
perché le aziende usano VLAN

# 14 - VLAN e Switching professionale

Finora abbiamo visto:

- IP
- subnet
- ARP
- DHCP
- routing

Ora entriamo nel mondo delle reti aziendali.

Una rete professionale non mette tutti i dispositivi insieme.

Viene divisa.

La tecnologia principale per farlo è:



VLAN


---

# Cos'è una VLAN?

VLAN significa:



Virtual Local Area Network


È una rete logica dentro una rete fisica.

In pratica:

Uno switch fisico può contenere più reti separate.

---

# Senza VLAN

Immagina uno switch:


          SWITCH


PC1
PC2
PC3
PC4
Server
Stampante
Telefono IP
Telecamera


Tutti sono nella stessa rete.

Problemi:

- troppo broadcast
- poca sicurezza
- difficile gestione

---

# Con VLAN

Lo stesso switch diventa:



VLAN 10

PC Uffici

VLAN 20

Server

VLAN 30

Telecamere


Fisicamente:



1 switch


Logicamente:



3 reti separate


---

# VLAN = separazione Layer 2

Una VLAN crea un dominio separato.

Ricorda:



VLAN

=

separazione Layer 2


Ogni VLAN ha:

- proprio broadcast domain
- propri MAC address
- propria rete IP

---

# Esempio aziendale

Azienda:



Switch principale


VLAN:



10

Amministrazione

20

Server

30

VoIP

40

Guest WiFi


---

# Broadcast Domain

Un broadcast è un messaggio:



a tutti


Esempio:

ARP Request:



Chi ha 192.168.1.1?


Senza VLAN:



tutti ricevono


Con VLAN:

solo:



dispositivi nella stessa VLAN


---

# VLAN ID

Ogni VLAN ha un numero.

Range:



1 - 4094


Esempio:



VLAN 10

VLAN 20

VLAN 100


---

# VLAN 1

Molti switch hanno:



VLAN 1


come VLAN predefinita.

Buona pratica:

non usarla per traffico importante.

---

# Access Port

Una porta access appartiene a una sola VLAN.

Esempio:

Porta switch:



Gi0/1


configurata:



VLAN 10


Colleghi:



PC


Il PC non sa nulla della VLAN.

---

Schema:



PC

|

Access Port

|

VLAN 10


---

# Trunk Port

Un trunk trasporta più VLAN contemporaneamente.

Esempio:

Collegamento tra switch:



Switch A

=========

Switch B


Su questo cavo passano:



VLAN 10

VLAN 20

VLAN 30


---

# Perché serve il trunk?

Senza trunk:

Servirebbe:



un cavo per ogni VLAN


Esempio:



Switch A

VLAN10 ---- cavo ---- VLAN10

VLAN20 ---- cavo ---- VLAN20

VLAN30 ---- cavo ---- VLAN30


Troppi cavi.

---

Con trunk:



un solo cavo

porta tutte le VLAN


---

# VLAN Tagging

Problema:

Come fa lo switch a sapere a quale VLAN appartiene un frame?

Usa:



802.1Q


---

# IEEE 802.1Q

È lo standard VLAN.

Aggiunge un tag Ethernet.

Prima:



Ethernet Frame

MAC

IP

DATA


Dopo:



Ethernet Frame

MAC

VLAN TAG

IP

DATA


---

# Contenuto del VLAN Tag

Contiene:



VLAN ID


Esempio:



Frame

VLAN:

20


Lo switch sa:



Questo traffico appartiene alla VLAN 20


---

# Access vs Trunk

## Access

Un dispositivo finale:



PC

Server

Stampante


Una VLAN.

---

## Trunk

Dispositivi di rete:



Switch

Router

Firewall

Access Point


Molte VLAN.

---

# Native VLAN

Su un trunk:

Le frame normalmente hanno tag.

La Native VLAN invece viaggia senza tag.

Esempio:



Trunk

VLAN 10 tagged

VLAN 20 tagged

Native VLAN untagged


---

# Perché esiste Native VLAN?

Compatibilità con vecchi dispositivi.

Buona pratica:

Cambiarla da VLAN 1.

---

# Inter-VLAN Routing

Una VLAN non comunica automaticamente con un'altra.

Esempio:



VLAN 10

192.168.10.0/24

VLAN 20

192.168.20.0/24


Sono separate.

Serve:



Router

oppure

Layer 3 Switch


---

# Router on a Stick

Metodo storico.

Schema:



VLAN 10

|


Switch

|


Trunk

|


Router

|


VLAN 20


Il router usa interfacce virtuali.

---

# Subinterface

Esempio:

Router:



G0/0.10

VLAN 10




G0/0.20

VLAN 20


---

# Layer 3 Switch

Gli switch moderni possono fare routing.

Un unico dispositivo:



Switch

Router


---

Esempio:



VLAN 10

  |


Layer 3 Switch

  |


VLAN 20


---

# VLAN e sicurezza

Scenario:

Azienda:



Dipendenti

Server

Guest


Separiamo:



VLAN 10

Utenti




VLAN 20

Server




VLAN 30

Ospiti


Poi firewall:



Guest

X

Server


---

# Voice VLAN

I telefoni IP hanno bisogno di una VLAN dedicata.

Esempio:



VLAN 10

PC




VLAN 50

Telefono VoIP


---

Schema:



PC

|

Telefono IP

|

Switch


Il telefono riceve traffico voce separato.

---

# VLAN e WiFi

Anche il WiFi usa VLAN.

Esempio:

SSID:



Azienda


↓

VLAN 10


SSID:



Guest


↓

VLAN 100

---

# VLAN Hopping

Attacco dove un dispositivo cerca di accedere ad altre VLAN.

Tecniche:

- Double Tagging
- Switch Spoofing

---

# Protezioni VLAN

## Disabilitare porte inutilizzate

Una porta libera è un rischio.

---

## Cambiare Native VLAN

Non usare:



VLAN 1


---

## Limitare trunk

Un trunk deve trasportare solo VLAN necessarie.

---

# MAC Address Table dello switch

Uno switch impara:



MAC

=

porta


Esempio:



AA:BB:CC

porta 5


---

# Come impara?

Quando riceve un frame:

Legge:



MAC sorgente


Salva:



Questo MAC è arrivato dalla porta X


---

# Forwarding

Se conosce il MAC:



manda solo alla porta corretta


Se non lo conosce:



flooding


---

# Flooding

Lo switch invia a tutte le porte della VLAN.

Tranne:



porta originale


Succede con:

- MAC sconosciuti
- broadcast

---

# Broadcast e VLAN

Ogni VLAN ha il suo broadcast.

Esempio:

VLAN 10:



broadcast solo VLAN 10


VLAN 20:



broadcast solo VLAN 20


---

# STP (Spanning Tree Protocol)

Problema:

Gli switch possono creare loop.

Esempio:



Switch A

|

Switch B

|

Switch C

|

Switch A


Il traffico gira infinito.

---

Soluzione:



STP


blocca collegamenti ridondanti.

---

# Loop di rete

Senza STP:



Broadcast

↓

Switch

↓

Switch

↓

Switch

↓

infinito


Risultato:



Broadcast Storm


---

# Switch professionale

Uno switch aziendale gestisce:

- VLAN
- Trunk
- STP
- QoS
- Security
- PoE
- Monitoring

---

# Comandi Cisco esempio

Vedere VLAN:



show vlan brief


---

Vedere trunk:



show interfaces trunk


---

Tabella MAC:



show mac address-table


---

Configurare VLAN:



vlan 10

name USERS


---

Porta access:



switchport mode access

switchport access vlan 10


---

Porta trunk:



switchport mode trunk


---

# Diagnosi VLAN

Problema:

"Due PC non comunicano"

Controllare:



Stessa VLAN?

Porta access corretta?

Trunk configurato?

Tag VLAN corretto?

Routing presente?


---

# Mentalità Network Engineer

Uno switch non collega semplicemente cavi.

Gestisce:



identità Layer 2

segmentazione

sicurezza

percorsi Ethernet


---

# Concetto chiave

Ricorda:



Switch:

MAC

VLAN:

separa reti Layer 2

Trunk:

trasporta VLAN

Router:

collega VLAN diverse


---

# Fine Capitolo 14

Prossimo capitolo:

# 15 - Firewall e sicurezza di rete

Argomenti:

- cosa fa veramente un firewall
- stateful inspection
- regole firewall
- porte e protocolli
- NAT
- DMZ
- IDS/IPS
- segmentazione sicurezza
- principi Zero Trust

# 15 - Firewall e sicurezza di rete

Una rete funzionante non basta.

Una rete professionale deve essere:

- disponibile
- controllata
- monitorata
- protetta

Il dispositivo principale che controlla il traffico tra reti è:



Firewall


---

# Cos'è un Firewall?

Un firewall è un sistema che decide:



quale traffico può passare

e

quale traffico deve essere bloccato


Lavora applicando:



regole di sicurezza


---

# Analogia semplice

Immagina un edificio.

Senza controllo:



chiunque entra


Con una guardia:



controllo accessi

↓

permesso o rifiuto


Il firewall è la guardia della rete.

---

# Dove si trova un Firewall?

Normalmente tra reti con diverso livello di fiducia.

Esempio:



Internet

|

Firewall

|

Rete interna


---

# Zone di rete

Una rete moderna viene divisa in zone.

Esempio:



INTERNET

|

DMZ

|

LAN

|

DATABASE


Ogni zona ha regole diverse.

---

# Tipi di Firewall

## Packet Filtering Firewall

Il firewall più semplice.

Controlla:

- IP sorgente
- IP destinazione
- porta
- protocollo

Esempio:



Permetti:

TCP 443

verso server web


---

# Stateful Firewall

È lo standard moderno.

Non guarda solo il pacchetto.

Tiene memoria delle connessioni.

---

Esempio:

Client:



apre connessione HTTPS


Firewall registra:



Connessione TCP attiva


Quando torna la risposta:



la riconosce

e la permette


---

# Stateless vs Stateful

## Stateless

Ogni pacchetto è valutato da solo.

Problema:

Non sa il contesto.

---

## Stateful

Conosce:



chi ha iniziato

stato connessione

risposta prevista


Molto più sicuro.

---

# Tabella delle connessioni

Un firewall stateful mantiene:



IP sorgente

porta sorgente

IP destinazione

porta destinazione

stato TCP


Esempio:



192.168.1.10:50000

↓

8.8.8.8:443

ESTABLISHED


---

# Regole Firewall

Una regola contiene:



Sorgente

Destinazione

Protocollo

Porta

Azione


---

Esempio:

Permettere web:



Source:

LAN

Destination:

Internet

Protocol:

TCP

Port:

443

Action:

ALLOW


---

# Deny e Allow

Due azioni principali:

## Allow

Permetti.

---

## Deny

Blocca.

---

# Ordine delle regole

Molti firewall leggono:



dall'alto verso il basso


Esempio:

Regola 1:



Blocca tutto


Regola 2:



Permetti HTTPS


La seconda non verrà mai raggiunta.

---

Regola corretta:



Permetti necessario

Blocca il resto


---

# Default Deny

Principio fondamentale:



Tutto bloccato

tranne ciò che autorizziamo


Questo è più sicuro.

---

# Porte comuni da proteggere

## SSH



TCP 22


Rischio:

tentativi di accesso.

---

## HTTP



TCP 80


---

## HTTPS



TCP 443


---

## RDP



TCP 3389


Molto attaccato.

---

# Firewall e NAT

Spesso firewall e NAT lavorano insieme.

Esempio:

Rete interna:



192.168.1.50


IP pubblico:



93.x.x.x


Il firewall traduce:



Privato

↓

Pubblico


---

# Port Forwarding

Permette accesso dall'esterno.

Esempio:

Internet:



utente


↓

Firewall:



porta 443


↓

Server interno:



10.0.0.10


---

# DMZ

DMZ significa:



Demilitarized Zone


È una rete separata per servizi pubblici.

Esempio:

Server web:



DMZ


Database:



LAN interna


---

Schema:



Internet

|

Firewall

|

DMZ

|

Firewall

|

LAN


---

# Perché usare DMZ?

Se il server web viene compromesso:

l'attaccante non deve arrivare direttamente ai database.

---

# IDS

IDS significa:



Intrusion Detection System


Rileva attività sospette.

Esempio:



1000 tentativi SSH


Genera:



Allarme


---

# IPS

IPS significa:



Intrusion Prevention System


Fa un passo in più.

Non solo rileva:



blocca automaticamente


---

# IDS vs IPS

|IDS|IPS|
|-|-|
|Rileva|Rileva|
|Avvisa|Blocca|
|Passivo|Attivo|

---

# Deep Packet Inspection

I firewall moderni possono analizzare:

non solo:



porta


ma anche:



contenuto applicativo


---

Esempio:

Traffico:



TCP 443


Normalmente consentito.

Ma il firewall può vedere:



malware nascosto dentro HTTPS


---

# Next Generation Firewall (NGFW)

Firewall moderni includono:

- controllo applicazioni
- antivirus
- IDS/IPS
- filtraggio URL
- analisi traffico
- threat intelligence

---

# VPN

Una VPN crea un tunnel sicuro.

Schema:



Computer remoto

  |


Internet

  |


Firewall

  |


Azienda


---

# Tipi di VPN

## Site-to-Site

Collega due reti.

Esempio:



Sede Milano

↓

VPN

↓

Sede Roma


---

## Remote Access VPN

Collega un utente.

Esempio:



Laptop dipendente

↓

VPN

↓

Azienda


---

# Crittografia VPN

Una VPN protegge:

- riservatezza
- integrità
- autenticazione

---

# Zero Trust

Modello moderno di sicurezza.

Principio:



Non fidarti mai.

Verifica sempre.


---

Prima:



Dentro rete = fidato


Ora:



Ogni richiesta deve essere verificata


---

# Microsegmentazione

La rete viene divisa in piccoli segmenti.

Esempio:

Prima:



tutta azienda


Dopo:



Utenti

Server

Database

Applicazioni

Backup


---

# Firewall nel Cloud

Nel cloud il firewall può essere:

- virtuale
- gestito dal provider
- software

Esempio:



Internet

↓

Security Group

↓

Virtual Machine


---

# Security Group

Molti cloud usano regole per macchina.

Esempio:

Server web:

Permetti:



TCP 443


Blocca:



tutto il resto


---

# Firewall Linux

Linux usa:

## iptables

Sistema storico.

---

## nftables

Sistema moderno.

---

Vedere regole:

```bash
sudo nft list ruleset

UFW

Firewall semplice Ubuntu.

Stato:

sudo ufw status


Abilitare:

sudo ufw enable


Permettere SSH:

sudo ufw allow 22


Permettere HTTPS:

sudo ufw allow 443

Log Firewall

Un firewall senza log è cieco.

Controllare:

tentativi bloccati
porte attaccate
anomalie

Esempio:

10000 richieste SSH

da stesso IP


Possibile attacco.

Principio del minimo privilegio

Regola fondamentale:

Permetti solo ciò che serve.


Esempio:

Server database:

Non deve avere:

porta 80 pubblica

Hardening Firewall

Buone pratiche:

cambiare password amministratore
aggiornare firmware
disabilitare servizi inutili
usare MFA
limitare accessi
monitorare log
Diagnosi firewall

Problema:

"Il server non risponde"

Controllare:

1.

Server acceso?


2.

IP corretto?


3.

Routing corretto?


4.

Firewall blocca?


5.

Porta aperta?

Strumenti utili

Test porta:

nc -vz IP PORTA


Scansione:

nmap IP


Connessioni:

ss -tulnp

Mentalità Network Engineer

Un firewall non deve essere:

un muro enorme


Deve essere:

un controllo intelligente


La sicurezza corretta è:

visibilità

+

regole precise

+

monitoraggio

+

riduzione superficie attacco

Concetto chiave

Ricorda:

Router:

decide dove va il traffico


Switch:

porta il traffico nella LAN


Firewall:

decide se il traffico è autorizzato

Fine Capitolo 15

Prossimo capitolo:

16 - Linux Networking per Network Engineer

Argomenti:

interfacce di rete
IP avanzato
routing Linux
firewall Linux
bridge
bonding
VLAN Linux
tcpdump
Wireshark
troubleshooting professionale

# 16 - Linux Networking per Network Engineer

Un vero network engineer deve conoscere Linux.

Perché?

Perché oggi moltissima infrastruttura gira su Linux:

- server web
- cloud
- container
- firewall
- router virtuali
- sistemi di monitoraggio
- Kubernetes
- appliance di rete

Linux permette di vedere e controllare quasi tutto.

---

# La filosofia Linux della rete

In Linux tutto passa attraverso:



interfacce

indirizzi

route

socket

pacchetti


La rete non è magia.

È configurazione.

---

# Le interfacce di rete

Un'interfaccia rappresenta una connessione.

Esempi:



eth0

ens33

enp0s3

wlan0


---

# Vedere le interfacce

Comando moderno:

```bash
ip link


Esempio:

1: lo

2: eth0

Loopback

Ogni sistema Linux ha:

lo


È l'interfaccia interna.

IP:

127.0.0.1


Serve per comunicare con se stesso.

Visualizzare indirizzi IP

Comando:

ip addr


Esempio:

eth0

inet 192.168.1.50/24


Significa:

IP:

192.168.1.50


Subnet:

/24

Aggiungere un IP manualmente

Esempio:

sudo ip addr add 192.168.1.100/24 dev eth0

Rimuovere un IP
sudo ip addr del 192.168.1.100/24 dev eth0

Attivare interfaccia
sudo ip link set eth0 up

Disattivare interfaccia
sudo ip link set eth0 down

MAC Address

Ogni scheda ha un MAC.

Vederlo:

ip link


Esempio:

link/ether

aa:bb:cc:dd:ee:ff

Routing Linux

Linux può funzionare come router.

La tabella routing decide:

dove mandare i pacchetti


Vedere routing:

ip route


Esempio:

default via 192.168.1.1

192.168.1.0/24 dev eth0

Default Route

La route più importante:

default


Significa:

se non so dove andare

manda qui


Esempio:

default via 192.168.1.1

Aggiungere una route

Esempio:

sudo ip route add 10.10.0.0/16 via 192.168.1.2

Rimuovere una route
sudo ip route del 10.10.0.0/16

IP Forwarding

Un Linux può diventare router.

Controllo:

cat /proc/sys/net/ipv4/ip_forward


Risultato:

0


disabilitato.

Abilitare:

sudo sysctl -w net.ipv4.ip_forward=1


Ora Linux inoltra pacchetti.

Esempio Linux Router

Schema:

Rete A

192.168.1.0/24

        |

      Linux

        |

Rete B

10.0.0.0/24


Linux collega due reti.

DNS Linux

Vedere configurazione:

cat /etc/resolv.conf


Esempio:

nameserver 8.8.8.8

Test DNS
dig google.com


oppure:

nslookup google.com

Hostname

Nome della macchina:

hostname


Informazioni complete:

hostnamectl

File hosts

Prima del DNS esiste:

/etc/hosts


Esempio:

192.168.1.10 server01


Quando chiedi:

server01


Linux cerca qui.

Ordine risoluzione nomi

Configurazione:

/etc/nsswitch.conf


Esempio:

hosts:

files dns


Significa:

prima:

/etc/hosts


poi:

DNS

Porte aperte Linux

Vedere servizi in ascolto:

ss -tulnp


Esempio:

LISTEN

0.0.0.0:22


SSH aperto.

Differenza LISTEN e ESTABLISHED

LISTEN:

servizio pronto


Esempio:

SSH aspetta connessioni


ESTABLISHED:

connessione attiva


Esempio:

utente collegato via SSH

Processo associato alla porta

Comando:

ss -tulnp


Mostra:

porta

PID

programma

TCP Dump

Uno degli strumenti più importanti.

Nome:

tcpdump


Serve per catturare pacchetti.

Installazione:

sudo apt install tcpdump


Catturare traffico:

sudo tcpdump


Specificare interfaccia:

sudo tcpdump -i eth0

Filtrare traffico

Solo DNS:

sudo tcpdump port 53


Solo HTTPS:

sudo tcpdump port 443


Solo un IP:

sudo tcpdump host 8.8.8.8

Salvare cattura

Formato:

.pcap


Comando:

sudo tcpdump -w traffico.pcap


Poi analizzabile con:

Wireshark

Wireshark

È lo strumento grafico più famoso.

Permette di vedere:

Ethernet
IP
TCP
DNS
HTTP
TLS
Filtri Wireshark

Esempi:

Solo DNS:

dns


Solo TCP:

tcp


Solo IP:

ip.addr == 192.168.1.10

ARP Linux

Vedere cache ARP:

ip neigh


Esempio:

192.168.1.1

lladdr

aa:bb:cc

Ping

Ping usa:

ICMP


Test:

ping 8.8.8.8


Risultato:

reply


significa:

IP raggiungibile.

Traceroute Linux

Mostra gli hop.

Installazione:

sudo apt install traceroute


Uso:

traceroute google.com

Firewall Linux

Linux usa principalmente:

nftables


e:

iptables

UFW

Interfaccia semplice.

Stato:

sudo ufw status


Bloccare tutto:

sudo ufw default deny


Permettere SSH:

sudo ufw allow ssh


Permettere HTTP:

sudo ufw allow 80

VLAN su Linux

Linux può creare interfacce VLAN.

Esempio:

Interfaccia:

eth0


VLAN:

100


Creazione:

sudo ip link add link eth0 name eth0.100 type vlan id 100


Attivazione:

sudo ip link set eth0.100 up

Bridge Linux

Un bridge collega interfacce come uno switch.

Esempio:

eth0

 |

Bridge

 |

VM


Usato da:

virtualizzazione
container
cloud

Vedere bridge:

bridge link

Bonding

Bonding significa:

unire più schede di rete.

Esempio:

Due NIC:

eth0

+

eth1


diventano:

bond0


Vantaggi:

Ridondanza

Se una scheda muore:

l'altra continua.

Performance

Possibile aumento banda.

NetworkManager

Molte distribuzioni moderne usano:

NetworkManager


Comando:

nmcli


Vedere connessioni:

nmcli connection show


Vedere dispositivi:

nmcli device

Netplan Ubuntu

Ubuntu Server usa spesso:

/etc/netplan/


Esempio:

01-network.yaml


Applicare configurazione:

sudo netplan apply

Troubleshooting Linux Network

Metodo professionale:

Livello 1

Fisico:

cavo

scheda

link


Comando:

ip link

Livello 2

Ethernet:

MAC

ARP

VLAN


Comando:

ip neigh

Livello 3

IP:

indirizzo

routing


Comandi:

ip addr

ip route

Livello 4

Trasporto:

porte

TCP

UDP


Comando:

ss

Livello 5+

Applicazione:

DNS

HTTP

SSH


Comandi:

dig

curl

ssh

Test completo connessione

Esempio:

Problema:

"Non raggiungo il sito"

Sequenza:

Controllo IP:

ip addr


Controllo gateway:

ip route


Ping gateway:

ping gateway


Ping Internet:

ping 8.8.8.8


Test DNS:

dig google.com


Test porta:

nc -vz google.com 443

Mentalità Network Engineer Linux

Non usare tentativi casuali.

Segui sempre:

Fisico

↓

Ethernet

↓

IP

↓

Routing

↓

TCP/UDP

↓

Applicazione

Concetto chiave

Ricorda:

ip addr

=

chi sono


ip route

=

dove vado


ss

=

chi parla


tcpdump

=

cosa succede realmente

Fine Capitolo 16

Prossimo capitolo:

17 - IPv6: il futuro delle reti

Argomenti:

perché nasce IPv6
indirizzi IPv6
compressione
subnet IPv6
SLAAC
DHCPv6
Neighbor Discovery
differenze IPv4/IPv6
sicurezza IPv6

# 17 - IPv6: il futuro delle reti

Per diventare un network engineer completo bisogna capire IPv6.

Molti conoscono solo IPv4, ma Internet sta usando sempre più IPv6.

Il motivo principale:



gli indirizzi IPv4 stanno finendo


---

# Il problema di IPv4

IPv4 usa:



32 bit


Esempio:



192.168.1.10


Numero massimo:



2^32

=

circa 4,3 miliardi di indirizzi


---

# Perché non bastano?

Oggi abbiamo:

- computer
- smartphone
- server
- IoT
- telecamere
- automobili
- dispositivi intelligenti

Ogni dispositivo vuole un indirizzo.

---

# Soluzioni temporanee IPv4

Prima di IPv6 sono stati creati:

## NAT

Condivisione di IP pubblici.

---

## Private IP

Indirizzi interni:



10.0.0.0/8

172.16.0.0/12

192.168.0.0/16


---

Problema:

IPv4 diventa sempre più complesso.

---

# Nasce IPv6

IPv6 usa:



128 bit


Esempio:



2001:0db8:85a3::8a2e:0370:7334


---

# Dimensione IPv6

Numero totale:



2^128


È un numero enorme.

Permette:



miliardi di miliardi di reti


---

# Differenza IPv4 e IPv6

|IPv4|IPv6|
|-|-|
|32 bit|128 bit|
|4 miliardi IP|quantità enorme|
|NAT comune|NAT meno necessario|
|Broadcast|Multicast|
|ARP|Neighbor Discovery|
|Configurazione spesso DHCP|SLAAC possibile|

---

# Struttura IPv6

Un indirizzo IPv6 è diviso in gruppi:

Esempio:



2001:0db8:1234:0001:0000:0000:0000:0001


Ogni gruppo è:



16 bit


---

# Notazione esadecimale

IPv6 usa:



0-9

a-f


Esempio:



2001:db8::1


---

# Compressione IPv6

Gli zeri possono essere abbreviati.

Prima:



2001:0db8:0000:0000:0000:0000:0000:0001


Dopo:



2001:db8::1


---

# Regola del doppio ::

Il simbolo:



::


può sostituire una sequenza di zeri.

Può essere usato una sola volta.

Corretto:



2001:db8::1


Errato:



2001::db8::1


---

# Tipi di indirizzi IPv6

IPv6 usa categorie diverse.

---

# Global Unicast

Indirizzo pubblico Internet.

Esempio:



2000::/3


Paragonabile a IPv4 pubblico.

---

# Link Local

Ogni dispositivo IPv6 ha automaticamente un indirizzo locale.

Range:



fe80::/10


Serve per comunicare nella stessa rete.

---

# Unique Local Address

Simile alle reti private IPv4.

Range:



fc00::/7


---

# Loopback IPv6

Come:



127.0.0.1


in IPv4.

IPv6:



::1


---

# Unspecified Address

Significa:

"nessun indirizzo"

IPv6:



::


---

# Broadcast non esiste

IPv4 usa:



255.255.255.255


IPv6 elimina il broadcast.

Usa:



multicast


---

# Multicast

Un pacchetto va:



a un gruppo specifico


Esempio:



tutti i router IPv6


---

# Subnet IPv6

IPv6 usa quasi sempre:



/64


Esempio:



2001:db8:abcd:0010::/64


Significa:

Primi:



64 bit


rete.

Ultimi:



64 bit


host.

---

# Perché /64?

Perché ogni rete IPv6 può avere:



2^64 dispositivi


Un numero enorme.

---

# Esempio rete IPv6

Rete:



2001:db8:1000::/64


Dispositivo 1:



2001:db8:1000::1


Dispositivo 2:



2001:db8:1000::2


---

# Configurazione IPv6

Esistono tre metodi.

---

# Metodo 1 - Statico

Configurazione manuale.

Esempio:



IPv6:

2001:db8::10/64

Gateway:

2001:db8::1


---

# Metodo 2 - DHCPv6

Come DHCP IPv4.

Il server assegna:

- indirizzo
- DNS
- parametri rete

---

# Metodo 3 - SLAAC

Il più interessante.

SLAAC significa:



Stateless Address Autoconfiguration


---

Il dispositivo:

1.

Riceve informazioni dal router

2.

Costruisce il proprio indirizzo

3.

Si configura automaticamente

---

# Router Advertisement

Il router invia:



RA

Router Advertisement


Dice:



Questa è la rete IPv6


---

Esempio:

Router:



2001:db8:10::/64


PC crea:



2001:db8:10::abcd


---

# Neighbor Discovery Protocol

IPv6 sostituisce ARP.

Si chiama:



NDP

Neighbor Discovery Protocol


Usa:



ICMPv6


---

# ARP vs NDP

IPv4:



ARP

IP → MAC


IPv6:



NDP

IP → MAC


---

# Come trova il MAC IPv6?

Il dispositivo chiede:



Chi possiede questo IPv6?


Risposta:



Sono io.
Questo è il mio MAC.


---

# ICMPv6

È fondamentale.

Usato per:

- ping IPv6
- Neighbor Discovery
- Router Advertisement
- diagnostica

---

# Ping IPv6

Comando:

```bash
ping6 ipv6.google.com


oppure:

ping -6 ipv6.google.com

Visualizzare IPv6 Linux

Comando:

ip -6 addr


Routing IPv6:

ip -6 route

DNS e IPv6

DNS supporta IPv6.

Record:

AAAA


Esempio:

server.com

AAAA

2001:db8::10

Connessione dual stack

Molte reti usano:

IPv4

+

IPv6


insieme.

Si chiama:

Dual Stack

Esempio Dual Stack

Server:

IPv4:

93.10.10.10


IPv6:

2001:db8::10


Il client sceglie.

Happy Eyeballs

I sistemi moderni provano:

IPv6:

prima


e IPv4:

se serve


Scelgono la connessione migliore.

IPv6 Security

IPv6 cambia alcune cose.

Errore comune

Pensare:

IPv6 = automaticamente sicuro


Falso.

IPv6 necessita comunque:

firewall
controllo accessi
monitoraggio
Firewall IPv6

Bisogna filtrare:

IPv4
IPv6

Errore comune:

proteggere IPv4 e dimenticare IPv6.

Privacy Extension

IPv6 può generare indirizzi temporanei.

Serve per:

ridurre il tracciamento.

EUI-64

Metodo storico per creare parte dell'indirizzo usando il MAC.

Esempio:

MAC:

aa:bb:cc:dd:ee:ff


diventa parte IPv6.

Oggi meno usato per privacy.

IPv6 nel Cloud

I cloud moderni supportano IPv6.

Esempio:

Server:

IPv6 pubblico


Firewall:

regole IPv6


DNS:

record AAAA

Troubleshooting IPv6

Problema:

"IPv6 non funziona"

Controllare:

1

Indirizzo:

ip -6 addr

2

Route:

ip -6 route

3

Gateway:

default IPv6 route

4

DNS:

dig AAAA dominio.com

5

Ping:

ping6 indirizzo

Catturare IPv6

tcpdump:

tcpdump -6


Filtro:

tcpdump ip6

Concetto professionale

IPv6 non è semplicemente:

più indirizzi


È un nuovo modo di progettare reti:

meno NAT
autoconfigurazione
multicast avanzato
gerarchia migliore
Mentalità Network Engineer

Quando guardi IPv6 pensa:

Indirizzo

↓

Subnet /64

↓

Neighbor Discovery

↓

Routing

↓

Firewall

↓

Applicazione

Concetto chiave

Ricorda:

IPv4:

usa ARP e spesso NAT


IPv6:

usa NDP e indirizzi enormi


DNS:

usa record A per IPv4

usa record AAAA per IPv6

Fine Capitolo 17

Prossimo capitolo:

18 - Wireshark e analisi dei pacchetti

Argomenti:

come leggere un pacchetto reale
Ethernet frame
header IP
TCP handshake visto dal vivo
filtri professionali
troubleshooting con packet capture
capire la rete "come un hacker"

# 18 - Wireshark e analisi dei pacchetti

Un network engineer avanzato non si limita a configurare reti.

Deve sapere:



cosa succede realmente dentro i pacchetti


Quando un utente dice:

"Internet è lento"

oppure:

"Il server non risponde"

la risposta spesso è nascosta nei pacchetti.

Lo strumento principale:



Wireshark


---

# Cos'è Wireshark?

Wireshark è un analizzatore di traffico di rete.

Permette di vedere:

- Ethernet
- ARP
- IPv4
- IPv6
- TCP
- UDP
- DNS
- HTTP
- TLS
- DHCP

---

# Packet Capture

Catturare pacchetti significa:



registrare il traffico che passa su una scheda di rete


Esempio:



Computer

|
|
Scheda Ethernet

|
|
Pacchetti


Wireshark osserva.

---

# Installazione Linux

Ubuntu:

```bash
sudo apt install wireshark


Avvio:

wireshark

Modalità Promiscuous

Normalmente una scheda vede:

solo il proprio traffico


Modalità promiscuous:

vede tutto il traffico che passa

Attenzione

Su reti moderne con switch:

non significa vedere automaticamente tutto.

Lo switch inoltra solo dove serve.

Per analizzare traffico altrui servono tecniche come:

port mirroring
TAP di rete
ambienti autorizzati
Struttura di un pacchetto

Ogni pacchetto è composto da livelli.

Esempio:

Ethernet

↓

IP

↓

TCP

↓

HTTP

↓

Dati

Layer 2 - Ethernet Frame

Primo livello visibile.

Contiene:

MAC sorgente

MAC destinazione

Tipo protocollo

Payload


Esempio:

MAC Dest:

Router


MAC Source:

PC

EtherType

Indica cosa c'è sopra Ethernet.

Esempi:

IPv4:

0x0800


IPv6:

0x86DD


ARP:

0x0806

Layer 3 - IP Header

Contiene:

IP sorgente

IP destinazione

TTL

Protocollo


Esempio:

192.168.1.10

↓

8.8.8.8

TTL

Ogni router diminuisce:

TTL -1


Serve per evitare loop.

Protocol Field

Dice cosa arriva dopo.

Esempi:

TCP:

6


UDP:

17


ICMP:

1

Layer 4 - TCP Header

Contiene:

porta sorgente

porta destinazione

sequence number

ack number

flag


Esempio:

192.168.1.10:52000

↓

142.250.x.x:443

TCP Flags

Le più importanti:

SYN

Inizio connessione.

ACK

Conferma ricezione.

FIN

Chiusura normale.

RST

Reset immediato.

Vedere un TCP Handshake

Filtro:

tcp.flags.syn == 1


Vedrai:

Client

SYN

↓

Server

SYN ACK

↓

Client

ACK

Analizzare una connessione HTTPS

Apri un sito.

Succede:

DNS

↓

TCP 443

↓

TLS

↓

HTTPS


In Wireshark vedrai:

DNS

Ricerca IP.

TCP

Apertura connessione.

TLS

Cifratura.

Application Data

Dati cifrati.

Filtri Wireshark fondamentali

Wireshark usa:

Display Filters

Filtrare IP

Un IP:

ip.addr == 192.168.1.10


Solo sorgente:

ip.src == 192.168.1.10


Solo destinazione:

ip.dst == 8.8.8.8

Filtrare porte

HTTPS:

tcp.port == 443


SSH:

tcp.port == 22


DNS:

udp.port == 53

Filtrare protocolli

DNS:

dns


HTTP:

http


TCP:

tcp


UDP:

udp


ARP:

arp

Seguire una conversazione TCP

Clic destro su pacchetto:

Follow

↓

TCP Stream


Wireshark ricostruisce:

tutta la conversazione

Esempio HTTP

Richiesta:

GET /index.html


Risposta:

HTTP 200 OK

DNS Packet Analysis

Quando apri:

google.com


vedi:

Client:

DNS Query

A google.com


Server:

DNS Response

142.x.x.x

DHCP Analysis

Filtro:

dhcp


Vedrai:

Discover

Offer

Request

ACK

ARP Analysis

Filtro:

arp


Esempio:

Richiesta:

Who has 192.168.1.1?


Risposta:

192.168.1.1 is aa:bb:cc

ICMP Analysis

Filtro:

icmp


Ping:

Echo Request

Echo Reply

TCP Retransmission

Uno dei problemi più importanti.

Filtro:

tcp.analysis.retransmission


Significa:

pacchetti persi o problemi rete

TCP Duplicate ACK

Filtro:

tcp.analysis.duplicate_ack


Può indicare:

perdita pacchetti
congestione
Slow Network Troubleshooting

Utente:

"La rete è lenta"

Non iniziare a cambiare configurazioni.

Analizza.

Controlla:

DNS

Tempo risposta:

alto?

TCP

Handshake lento:

ritardi?

Retransmission:
pacchetti persi?

Server:
risponde lentamente?

RTT

RTT significa:

Round Trip Time


Tempo:

andata + ritorno


Esempio:

Ping:

20 ms


Buono.

Ping:

500 ms


Problema.

Latency vs Bandwidth

Errore comune:

"Ho più banda quindi sarà più veloce"

Non sempre.

Bandwidth:

quantità dati


Esempio:

1 Gbps


Latency:

tempo necessario


Esempio:

20 ms

Packet Loss

Problema grave.

Esempio:

100 pacchetti inviati.

5 persi.

Loss:

5%


Può causare:

lentezza
ritrasmissioni
problemi VoIP
MTU

MTU significa:

Maximum Transmission Unit


Massima dimensione pacchetto.

Ethernet normalmente:

1500 byte

Problema MTU

Se troppo grande:

packet fragmentation


oppure:

connessioni bloccate


Test:

ping -M do -s 1472 google.com

Jumbo Frames

Alcune reti usano:

9000 byte


Sono comuni in:

storage
data center
Packet Capture da terminale

Con tcpdump:

sudo tcpdump -i eth0


Salvare:

sudo tcpdump -i eth0 -w rete.pcap


Leggere:

tcpdump -r rete.pcap

Analisi professionale

Quando catturi traffico chiediti:

Chi parla?
IP sorgente

Con chi?
IP destinazione

Come?
TCP

UDP

ICMP

Su quale servizio?
porta

Cosa succede?
errore?

ritrasmissione?

ritardo?

Esempio reale

Problema:

"SSH è lento"

Analisi:

Filtro:

tcp.port == 22


Controllo:

SYN

ACK

Delay

Retransmission


Possibili cause:

latenza
packet loss
firewall
DNS lento
Packet Analysis Mental Model

Ogni comunicazione:

Chi?

(IP)


Dove?

(porta)


Come?

(TCP/UDP)


Cosa?

(protocollo)


Problema?

(errori)

Diventare bravo con Wireshark

Esercizi:

Esercizio 1

Apri:

google.com


Trova:

DNS
TCP handshake
TLS
Esercizio 2

Fai:

ping 8.8.8.8


Trova:

ICMP request
ICMP reply
Esercizio 3

Avvia:

ssh server


Trova:

porta 22
handshake TCP
Mentalità Network Engineer

Un principiante dice:

"Non funziona"

Un network engineer guarda:

il pacchetto


Perché il pacchetto dice sempre la verità.

Concetto chiave

Ricorda:

Wireshark:

vede cosa succede realmente


tcpdump:

cattura dal terminale


Packet analysis:

trasforma problemi vaghi

in problemi misurabili

Fine Capitolo 18

Prossimo capitolo:

19 - Cloud Networking: AWS, Oracle Cloud, Azure e reti moderne

Argomenti:

VPC
subnet cloud
route table cloud
security group
load balancer
NAT gateway
Internet gateway
private subnet
architetture professionali cloud

# 19 - Cloud Networking: AWS, Oracle Cloud, Azure e reti moderne

Oggi un network engineer deve conoscere il cloud.

Le reti non sono più solo:



switch

router

cavi


Ora esistono:



reti virtuali

server virtuali

firewall software

load balancer

connessioni ibride


---

# Cos'è il Cloud Networking?

Il cloud networking è la progettazione di reti dentro un'infrastruttura cloud.

Concetti fondamentali:

- VPC / VCN
- subnet
- routing
- firewall
- NAT
- gateway
- bilanciamento traffico
- sicurezza

---

# La rete fisica del Cloud

Nel data center del provider esistono:



Server fisici

Switch fisici

Router fisici

Firewall fisici


Ma il cliente vede:



macchine virtuali

reti virtuali

indirizzi IP virtuali


---

# Virtualizzazione della rete

Prima:



Server

|

Switch fisico

|

Router


Cloud:



VM

|

Virtual Switch

|

Virtual Router

|

Internet


---

# VPC / VCN

Ogni cloud usa un nome diverso.

AWS:



VPC

Virtual Private Cloud


Oracle Cloud:



VCN

Virtual Cloud Network


Azure:



Virtual Network


Il concetto è lo stesso:



una rete privata isolata nel cloud


---

# Esempio VPC

Creiamo:



VPC

10.0.0.0/16


Dentro:



Subnet Web

10.0.1.0/24

Subnet Database

10.0.2.0/24


---

# CIDR nel Cloud

Il cloud usa CIDR.

Esempio:



10.0.0.0/16


Significa:

Rete:



10.0


Indirizzi disponibili:

circa:



65.534 host


---

# Subnet Cloud

Una subnet è una divisione della rete.

Esempio:



VPC

10.0.0.0/16

    |


Web

10.0.1.0/24

Database

10.0.2.0/24


---

# Public Subnet

Una subnet pubblica permette accesso Internet.

Esempio:



Internet

|

Web Server


Ha:

- IP pubblico
- route verso Internet Gateway

---

# Private Subnet

Una subnet privata non è direttamente raggiungibile.

Esempio:



Internet

X

Database


Usata per:

- database
- applicazioni interne
- sistemi sensibili

---

# Architettura professionale

Schema classico:


             Internet

                |

          Load Balancer

                |

          Web Servers

                |

        Application Servers

                |

          Database


---

# Internet Gateway

Permette comunicazione:



Cloud

<->

Internet


Esempio:

Server web:



10.0.1.10


tramite gateway:



IP pubblico


---

# NAT Gateway

Serve ai server privati per uscire.

Esempio:

Database:



10.0.2.10


deve scaricare aggiornamenti.

Non deve ricevere connessioni.

Usa:



NAT Gateway


---

Schema:



Private Server

  |


NAT Gateway

  |


Internet


---

# Differenza Internet Gateway e NAT Gateway

Internet Gateway:



entrata + uscita


NAT Gateway:



solo uscita


---

# Route Table Cloud

Come un router.

Decide:



dove mandare il traffico


---

Esempio:

Route pubblica:



0.0.0.0/0

↓

Internet Gateway


---

Route privata:



0.0.0.0/0

↓

NAT Gateway


---

# Security Group

Firewall associato alla macchina.

Controlla:

- porte
- protocolli
- sorgenti

---

Esempio:

Web Server:

Permetti:



TCP 443

da Internet


Blocca:



TCP 22


---

# Network ACL

Firewall a livello subnet.

Differenza:

Security Group:



singola macchina


Network ACL:



intera subnet


---

# Stato delle regole

Security Group:



stateful


Se permetti una richiesta:

la risposta torna automaticamente.

---

Network ACL:



stateless


Devi permettere entrambi i sensi.

---

# Load Balancer

Serve a distribuire traffico.

Problema:

Un solo server:



utente

|

server


Rischio:

- sovraccarico
- guasto

---

Con Load Balancer:


          Load Balancer

          /        \

      Server1    Server2


---

# Tipi Load Balancer

## Layer 4

Lavora con:

- IP
- TCP
- UDP

---

## Layer 7

Lavora con:

- HTTP
- URL
- cookie
- header

---

# Health Check

Il load balancer controlla:



il server è vivo?


Esempio:

Richiesta:



GET /health


Risposta:



200 OK


Server sano.

---

# Auto Scaling

Il cloud può creare server automaticamente.

Esempio:

Normale:



2 server


Molti utenti:



10 server


Pochi utenti:



2 server


---

# DNS nel Cloud

DNS dirige gli utenti.

Esempio:



www.sito.com


diventa:



Load Balancer IP


---

# Record DNS comuni

A:



IPv4


AAAA:



IPv6


CNAME:



alias


---

# Cloud Private IP

Dentro una rete cloud:

esempio:



10.0.1.50


È visibile solo internamente.

---

# Cloud Public IP

Visibile Internet.

Esempio:



140.x.x.x


---

# SSH nelle macchine cloud

Errore comune:

aprire:



SSH 22

da tutto Internet


Meglio:



SSH

solo dal proprio IP


---

# Bastion Host

Metodo professionale.

Non si entra direttamente nei server privati.

Schema:



Internet

|

Bastion

|

Private Servers


---

# VPN Cloud

Collega:

ufficio

↓

cloud

---

Esempio:



Sede aziendale

10.10.0.0/16

VPN

Cloud

10.20.0.0/16


---

# Direct Connect / FastConnect

Connessione privata al cloud.

Invece di:



Internet pubblico


usa:



collegamento dedicato


---

# Cloud Firewall

Può essere:

- Security Group
- Firewall virtuale
- WAF
- Network Firewall

---

# WAF

Web Application Firewall.

Protegge applicazioni web.

Blocca:

- SQL Injection
- XSS
- bot
- richieste malevole

---

# Database in Cloud

Buona pratica:

Mai:



Database pubblico Internet


Meglio:



Private Subnet

Database


---

# Esempio architettura sicura


             Internet

                |

              WAF

                |

         Load Balancer

                |

          Web Subnet

                |

        Application Subnet

                |

         Database Subnet


---

# Oracle Cloud Free Tier esempio

Una macchina gratuita tipica:



VM

Private IP

Subnet

VCN

Route Table

Security List


---

Flusso:



Internet

|

Public IP

|

Virtual NIC

|

VM

|

Linux


---

# Problemi comuni Cloud

## SSH non funziona

Controllare:



VM accesa

IP pubblico corretto

Security Rule porta 22

Firewall Linux

Chiave SSH


---

## Server senza Internet

Controllare:



Route Table

↓

NAT Gateway

↓

DNS


---

## Sito non raggiungibile

Controllare:



DNS

↓

Load Balancer

↓

Security Group

↓

Server

↓

Applicazione


---

# Monitoring Cloud

Un network engineer controlla:

- CPU
- RAM
- traffico
- errori
- latency
- packet drop

---

# Metriche importanti

## Bandwidth

Quanto traffico passa.

---

## Latency

Quanto tempo impiega.

---

## Throughput

Traffico realmente utilizzato.

---

## Packet Loss

Pacchetti persi.

---

# Infrastructure as Code

Nel cloud non si configura tutto manualmente.

Si usa:

- Terraform
- Ansible
- CloudFormation

---

Esempio:

Invece di creare:



VPC

Subnet

Firewall

Server


a mano:

scrivi:



codice

↓

infrastruttura


---

# Mentalità Cloud Network Engineer

Devi pensare:



Chi può entrare?

Chi può uscire?

Quale rete?

Quale subnet?

Quale route?

Quale firewall?

Quale log?


---

# Concetto chiave

Ricorda:



VPC/VCN

=

rete privata cloud

Subnet

=

segmentazione

Route Table

=

decisione percorso

Security Group

=

firewall macchina

NAT

=

uscita controllata

Load Balancer

=

distribuzione traffico


---

# Fine Capitolo 19

Prossimo capitolo:

# 20 - Docker, Container Networking e Kubernetes

Argomenti:

- cosa sono i container
- Docker network
- bridge network
- port mapping
- container DNS
- Kubernetes networking
- pod
- service
- ingress
- networking moderno DevOps

# 20 - Docker, Container Networking e Kubernetes

Il networking moderno non vive più solo dentro macchine virtuali.

Oggi gran parte delle applicazioni gira dentro:



container


e viene orchestrata con:



Kubernetes


Un network engineer moderno deve capire:

- come comunicano i container
- come vengono esposti su Internet
- come funzionano le reti Kubernetes

---

# Cos'è un Container?

Un container è un ambiente isolato che contiene:

- applicazione
- librerie
- dipendenze
- configurazione

Esempio:

Un'applicazione web:



Container

Nginx
+
Python
+
Database client


---

# Container vs Virtual Machine

## Virtual Machine

Ha:



Hardware virtuale

↓

Sistema operativo completo

↓

Applicazione


---

## Container

Ha:



Sistema operativo host

↓

Container runtime

↓

Applicazione


---

# Differenza principale

VM:



più pesante


Container:



più leggero


---

# Docker

Docker è una piattaforma per creare e gestire container.

Componenti:



Docker Engine

Docker Image

Docker Container

Docker Network


---

# Image

Una image è un modello.

Esempio:



nginx:latest


Contiene:



filesystem

configurazioni

software


---

# Container

Un container è una image in esecuzione.

Esempio:

Image:



nginx


diventa:



container nginx attivo


---

# Installare Docker Ubuntu

Esempio:

```bash
sudo apt update

sudo apt install docker.io -y


Avvia:

sudo systemctl start docker


Controlla:

docker version

Primo Container

Avviare nginx:

docker run nginx


Docker:

scarica image
crea container
avvia servizio
Container attivi
docker ps


Tutti:

docker ps -a

Fermare container
docker stop nome_container

Eliminare container
docker rm nome_container

Il problema della rete nei container

Ogni container deve poter comunicare.

Esempio:

Web Container

      |

Database Container


Serve networking.

Docker Networking

Docker crea reti virtuali.

Vedere reti:

docker network ls


Default:

bridge

Bridge Network

È la rete più comune.

Schema:

Host Linux

 |

Docker Bridge

 |

Container

Container IP

Ogni container riceve:

IP privato interno


Esempio:

172.17.0.2


Vedere IP:

docker inspect nome_container

Port Mapping

Problema:

Il container ha un IP interno.

Internet non lo vede.

Serve:

port forwarding


Esempio:

Container:

porta 80


Host:

porta 8080


Comando:

docker run -p 8080:80 nginx


Significa:

HOST:8080

↓

CONTAINER:80

Accesso

Browser:

http://IP_SERVER:8080


Arriva a:

nginx container

Docker DNS

I container nella stessa rete possono usare nomi.

Esempio:

Container:

web


Container:

database


Il web può chiamare:

database


invece di:

172.18.0.5

Creare rete Docker
docker network create mia_rete


Avviare container nella rete:

docker run --network mia_rete nginx

Docker Compose

Serve per definire più container.

Esempio:

Applicazione:

Web

+

Database

+

Cache


File:

docker-compose.yml


Definisce:

container
reti
volumi
porte
Esempio architettura Docker
             Internet

                |

              Nginx

                |

          Application Container

                |

          Database Container

Container Security

Problemi comuni:

container esposti
immagini vulnerabili
privilegi eccessivi
porte aperte inutilmente

Buone pratiche:

aggiornare immagini
usare utenti non root
limitare privilegi
scansionare immagini
Da Docker a Kubernetes

Quando hai:

1 container


Docker basta.

Quando hai:

1000 container


serve orchestrazione.

Kubernetes

Kubernetes gestisce:

creazione container
scalabilità
networking
aggiornamenti
ripristino automatico
Architettura Kubernetes

Componenti principali:

Control Plane

+

Worker Nodes

Node

Un nodo è una macchina che esegue container.

Può essere:

VM
server fisico
macchina cloud
Pod

L'unità base Kubernetes.

Un pod contiene:

uno o più container


Esempio:

Pod

 |
 +-- nginx container
 |
 +-- sidecar container

Ogni Pod ha un IP

Esempio:

10.244.1.20


Questo IP è interno al cluster.

Problema

I Pod cambiano.

Un pod può morire.

Il nuovo pod avrà:

IP diverso


Serve un sistema stabile.

Kubernetes Service

Un Service crea un indirizzo stabile.

Schema:

Client

 |

Service

 |

Pod Pod Pod


Il client non conosce i pod.

Conosce:

Service IP

Tipi Service Kubernetes
ClusterIP

Solo interno.

Esempio:

app interna

NodePort

Apre una porta sui nodi.

Esempio:

NodeIP:30080

LoadBalancer

Crea un bilanciatore cloud.

Esempio:

Internet

↓

Cloud Load Balancer

↓

Service

Kubernetes DNS

Ogni service ha un nome DNS.

Esempio:

database.default.svc.cluster.local

Kubernetes Networking Model

Regole fondamentali:

Ogni Pod:

può comunicare con ogni altro Pod


senza NAT.

Ogni Pod:

ha un IP unico


nel cluster.

CNI (Container Network Interface)

È il sistema che crea networking Kubernetes.

Esempi:

Calico
Flannel
Cilium
Ingress

Ingress gestisce traffico HTTP esterno.

Schema:

Internet

 |

Ingress Controller

 |

Service

 |

Pods


Esempio:

Domini:

api.sito.com

web.sito.com


Ingress decide:

api

↓

backend

web

↓

frontend

Kubernetes Network Policy

Firewall interno Kubernetes.

Permette:

chi può parlare con chi


Esempio:

Permetti:

Frontend

↓

Backend


Blocca:

Database

↓

Internet

Container Networking nel Cloud

Esempio:

Cloud:

VPC

 |

Kubernetes Cluster

 |

Nodes

 |

Pods

EKS / AKS / GKE

Kubernetes gestito:

AWS:

EKS


Azure:

AKS


Google:

GKE

Troubleshooting Container Network

Problema:

"Container non comunica"

Controllare:

Container attivo
docker ps

IP container
docker inspect

Network
docker network ls

Porte
ss -tulnp

DNS

Dentro container:

ping nome_container

Troubleshooting Kubernetes

Pod:

kubectl get pods


Service:

kubectl get svc


IP:

kubectl describe pod nome


Log:

kubectl logs nome_pod


Test dentro pod:

kubectl exec -it nome_pod -- bash

Mentalità Network Engineer Cloud Native

Devi pensare:

Prima:

Server

↓

IP

↓

Porta


Ora:

Container

↓

Pod

↓

Service

↓

Ingress

↓

Load Balancer

↓

Internet

Concetto chiave

Ricorda:

Docker:

crea container


Docker Network:

collega container


Kubernetes:

gestisce migliaia di container


Service:

crea indirizzo stabile


Ingress:

porta traffico HTTP dall'esterno

Fine Capitolo 20

Prossimo capitolo:

21 - Routing avanzato e protocolli dinamici

Argomenti:

come funzionano i router professionali
routing statico
routing dinamico
RIP
OSPF
BGP
Autonomous System
Internet backbone
come funziona davvero Internet

# 21 - Routing avanzato e protocolli dinamici

Il routing è il cuore di Internet.

Ogni volta che apri un sito, invii un messaggio o guardi un video:

milioni di router decidono:



dove mandare i pacchetti


Un network engineer deve capire come ragionano i router.

---

# Cos'è un Router?

Un router è un dispositivo Layer 3.

Il suo compito:



collegare reti diverse


Esempio:



LAN Azienda

192.168.1.0/24

    |

  Router

    |


Internet


---

# Switch vs Router

## Switch

Lavora con:



MAC Address


Dentro:



stessa rete


---

## Router

Lavora con:



IP Address


Tra:



reti diverse


---

# La Routing Table

Ogni router possiede una tabella.

Esempio:



Destinazione Gateway

192.168.1.0/24 diretto

10.0.0.0/8 192.168.1.2

0.0.0.0/0 ISP


---

# Come decide il router?

Riceve pacchetto:



Destinazione:

8.8.8.8


Controlla:



Ho una rotta?


Se sì:

manda lì.

---

# Longest Prefix Match

Regola fondamentale.

Il router sceglie la rotta:



più specifica


Esempio:

Rotte:



0.0.0.0/0

10.0.0.0/8

10.10.10.0/24


Destinazione:



10.10.10.50


Vince:



10.10.10.0/24


---

# Routing Statico

Una rotta inserita manualmente.

Esempio:



Rete A

|

Router

|

Rete B


Configurazione:



per raggiungere B usa questo gateway


---

Vantaggi:

- semplice
- prevedibile
- sicuro

---

Svantaggi:

- difficile con molte reti
- aggiornamento manuale

---

# Esempio Static Route Linux

```bash
ip route add 10.20.0.0/16 via 192.168.1.2

Routing Dinamico

Con molte reti serve automatizzazione.

I router comunicano tra loro.

Usano:

protocolli di routing
``` id="0b3p6z"

---

# Perché usare routing dinamico?

Immagina:



1000 router


Cambiare manualmente:



impossibile


---

Con routing dinamico:

I router imparano automaticamente.

---

# Autonomous System (AS)

Internet è divisa in grandi reti.

Ogni rete autonoma è:



Autonomous System


Esempi:

- ISP
- grandi aziende
- università
- cloud provider

---

Ogni AS ha un numero:



ASN

Autonomous System Number


Esempio:



AS12345


---

# IGP e EGP

I protocolli di routing si dividono in:

---

# IGP

Interior Gateway Protocol.

Dentro un'organizzazione.

Esempi:

- OSPF
- RIP
- EIGRP

---

# EGP

Exterior Gateway Protocol.

Tra organizzazioni.

Il principale:



BGP


---

# RIP

Routing Information Protocol.

Vecchio protocollo.

---

Funzionamento:

Usa:



numero di hop


Esempio:



Rete A

↓

Router 1

↓

Router 2

↓

Rete B


Costo:



2 hop


---

# Problemi RIP

Limiti:

- lento
- massimo 15 hop
- poco usato oggi

---

# OSPF

Open Shortest Path First.

È uno dei protocolli più importanti.

---

Usato in:

- aziende
- data center
- reti grandi

---

# Come funziona OSPF?

Ogni router:

1.

scopre vicini

2.

scambia informazioni

3.

crea una mappa della rete

4.

calcola percorso migliore

---

# Link State

OSPF è:



Link State Protocol


Ogni router conosce:



topologia completa


---

# Algoritmo SPF

OSPF usa:



Dijkstra


Per trovare:



percorso più breve


---

# OSPF Areas

Le reti grandi vengono divise.

Esempio:



Area 0

Backbone

|

Area 1

Uffici

|

Area 2

Data Center


---

# Area 0

È il cuore OSPF.

Tutte le altre aree devono collegarsi.

---

# OSPF Neighbor

I router creano relazioni.

Esempio:



Router A

HELLO

↓

Router B


Diventano:



neighbor


---

# Metric OSPF

OSPF usa:



costo


Basato principalmente sulla banda.

---

Esempio:

Link:



1 Gbps


preferito rispetto:



10 Mbps


---

# BGP

Border Gateway Protocol.

È il protocollo che muove Internet.

---

BGP collega:



Autonomous System

con

Autonomous System


---

Esempio:



ISP A

|

BGP

|

ISP B


---

# Perché BGP è diverso?

OSPF cerca:



percorso più veloce


BGP cerca:



percorso migliore secondo politica


---

# BGP usa gli AS Path

Esempio:

Rotta:



Rete X

AS100

AS200

AS300


BGP vede:



passa da 100,200,300


---

# Internet Routing

Quando visiti:



google.com


Il traffico può passare:



Casa

↓

ISP

↓

Carrier

↓

Google Network


Ogni AS usa BGP.

---

# Default Route

Molti router hanno:



0.0.0.0/0


Significa:



tutto il resto va qui


---

# Routing e Cloud

Nel cloud trovi concetti simili:



Route Table

Subnet

Gateway


Sono router virtuali.

---

# ECMP

Equal Cost Multi Path.

Permette più percorsi uguali.

Esempio:



Router

/ \

Link1 Link2


Traffico distribuito.

---

# VRF

Virtual Routing and Forwarding.

Permette più routing table sullo stesso router.

Esempio:



Router fisico

|

VRF Cliente A

VRF Cliente B


Usato dagli ISP.

---

# NAT e Routing

NAT cambia indirizzi.

Routing decide:



dove va il pacchetto


Sono concetti diversi.

---

# Routing Troubleshooting

Problema:

"Rete non raggiungibile"

Seguire:

---

## 1

Controlla IP:

```bash
ip addr

2

Controlla route:

ip route

3

Gateway:

ping gateway

4

Traccia percorso:

traceroute destinazione

5

Guarda routing:

dove si ferma il pacchetto?
``` id="k6w1zp"

---

# Traceroute

Mostra gli hop.

Esempio:



PC

|

Router casa

|

ISP

|

Google


---

# TTL e Traceroute

Traceroute sfrutta TTL.

Invia pacchetti con:



TTL 1

TTL 2

TTL 3


Ogni router risponde.

---

# Route Flapping

Problema:

Una rotta continua:



apparire

sparire


Effetti:

- instabilità
- perdita pacchetti

---

# Convergenza

Tempo necessario ai router per aggiornarsi.

Esempio:

Guasto link.

Quanto tempo serve?



convergenza


---

# Network Engineer Mentalità

Non chiederti solo:

"qual è l'IP?"

Chiediti:



chi conosce questa rete?

qual è il percorso?

qual è la rotta migliore?

dove cambia?


---

# Concetto chiave

Ricorda:



Switch:

MAC

Router:

IP

Routing Statico:

manuale

OSPF:

interno aziendale

BGP:

Internet


---

# Fine Capitolo 21

Prossimo capitolo:

# 22 - Alta disponibilità, ridondanza e reti enterprise

Argomenti:

- perché le reti non devono mai fermarsi
- failover
- HSRP
- VRRP
- clustering
- load balancing avanzato
- link aggregation
- data center networking
- progettazione enterprise

# 22 - Alta disponibilità, ridondanza e reti enterprise

Una rete professionale non può dipendere da un solo dispositivo.

Un router guasto.

Uno switch rotto.

Un collegamento interrotto.

Possono fermare:

- aziende
- ospedali
- banche
- servizi cloud

Per questo esiste:



High Availability (HA)


---

# Cos'è l'Alta Disponibilità?

Significa progettare sistemi che continuano a funzionare anche quando qualcosa si rompe.

Obiettivo:



eliminare il Single Point of Failure


---

# Single Point of Failure (SPOF)

Un singolo elemento la cui rottura causa il blocco.

Esempio:



Internet

|

UN SOLO ROUTER

|

Azienda


Se il router muore:



rete offline


---

# Ridondanza

La soluzione:

avere più elementi.

Esempio:

Prima:



Internet

|

Router


Dopo:


      Internet

      /     \

 Router1   Router2

      \     /

      LAN


---

# Tipi di ridondanza

## Hardware

Due dispositivi.

Esempio:



Firewall A

Firewall B


---

## Link

Più collegamenti.

Esempio:



Switch

|

Link1

|

Link2


---

## Alimentazione

Due alimentatori.

---

## Geografica

Più sedi.

Esempio:



Data Center Milano

Data Center Roma


---

# Availability

La disponibilità si misura in percentuale.

Esempio:



99%


significa:

circa:



3,65 giorni di downtime all'anno


---

# Tabelle Availability

## 99%

Downtime:



3,65 giorni


---

## 99,9%

"Three nines"

Downtime:



8,76 ore/anno


---

## 99,99%

"Four nines"

Downtime:



52 minuti/anno


---

## 99,999%

"Five nines"

Downtime:



5 minuti/anno


---

# Failover

Failover significa:

passaggio automatico a un sistema di backup.

Esempio:



Router principale

    X


Router secondario


Il traffico passa automaticamente.

---

# Active-Passive

Uno lavora.

Uno aspetta.

Schema:



Router A

ACTIVE

|

Router B

STANDBY


---

Se A muore:



Router B

ACTIVE


---

# Active-Active

Entrambi lavorano.

Schema:



Router A

Router B

=

traffico condiviso


---

Vantaggi:

- più capacità
- migliore utilizzo risorse

---

# First Hop Redundancy Protocol

Problema:

I client hanno un gateway.

Esempio:



PC

Gateway:

192.168.1.1


Ma cosa succede se il router gateway muore?

---

Soluzione:

FHRP.



First Hop Redundancy Protocol


---

# HSRP

Protocollo Cisco.



Hot Standby Router Protocol


---

Esempio:

Router:



Router A

192.168.1.2

Router B

192.168.1.3


Creano:



IP virtuale

192.168.1.1


---

I PC usano:



192.168.1.1


Non sanno quale router è attivo.

---

Se Router A cade:



Router B prende il controllo


---

# VRRP

Alternativa standard.



Virtual Router Redundancy Protocol


Funziona con molti vendor.

---

Schema:



Router A

\

Virtual IP

/

Router B


---

# GLBP

Protocollo Cisco.

Oltre al failover:

distribuisce traffico.

---

# Link Aggregation

Problema:

Un collegamento singolo può essere insufficiente.

Soluzione:

unire più link.

---

Tecnologia:



LACP


---

# LACP



Link Aggregation Control Protocol


---

Esempio:

Prima:



Switch

|

1 Gbps


---

Dopo:



Switch

|

1 Gbps
1 Gbps
1 Gbps

=

3 Gbps


---

# Vantaggi LACP

- più banda
- ridondanza
- gestione migliore

---

# EtherChannel

Nome Cisco per aggregazione porte.

Esempio:



Gi0/1

Gi0/2

Gi0/3

↓

Port-channel


---

# Spanning Tree e Ridondanza

Problema:

Avere più collegamenti crea loop.

Esempio:



Switch A

| |

| |

Switch B


---

Senza protezione:



loop infinito


---

STP risolve.



blocca un percorso


---

# STP



Spanning Tree Protocol


Decide:

- percorso principale
- collegamenti bloccati

---

# Root Bridge

STP sceglie uno switch principale.

Si chiama:



Root Bridge


---

Gli altri calcolano:



miglior percorso verso root


---

# RSTP

Versione veloce:



Rapid Spanning Tree Protocol


Converge più rapidamente.

---

# Data Center Networking

I data center richiedono:

- velocità
- ridondanza
- bassa latenza

---

Architettura moderna:


          Core

           |

      Distribution

           |

         Access


---

# Spine-Leaf Architecture

Molto usata nei data center.

Schema:


    Spine


/ | \

Leaf Leaf Leaf

| | |

Server Server Server


---

# Spine

Router/switch backbone.

---

# Leaf

Collega:

- server
- storage
- firewall

---

# Vantaggi Spine-Leaf

- latenza prevedibile
- scalabilità
- molti percorsi disponibili

---

# East-West Traffic

Nei data center gran parte del traffico è:



server

↓

server


Non:



utente

↓

server


---

Questo si chiama:



East-West Traffic


---

# North-South Traffic

Tra:



utente esterno

↓

data center


---

# Load Balancing Avanzato

Un load balancer moderno può distribuire:

- HTTP
- TCP
- UDP
- API
- database

---

# Algoritmi Load Balancer

## Round Robin

A rotazione.

Esempio:



Richiesta 1 → Server A

Richiesta 2 → Server B

Richiesta 3 → Server C


---

## Least Connections

Va al server con meno connessioni.

---

## Weighted

Server più potenti ricevono più traffico.

---

# Session Persistence

Problema:

Un utente deve restare sullo stesso server.

Soluzione:



Sticky Session


---

Esempio:

Cookie:



utente → Server A


---

# Database High Availability

Un database critico usa:

- replica
- cluster
- failover automatico

---

Esempio:



Database Master

   |


Replica

   |


Database Slave


---

# Backup vs Alta Disponibilità

Sono diversi.

Backup:



recupero dati


---

Alta disponibilità:



continuità servizio


---

# Disaster Recovery

Piano per eventi gravi.

Esempio:

Data center distrutto.

Soluzione:



secondo data center


---

# RPO e RTO

Concetti fondamentali.

---

# RPO

Recovery Point Objective.

Domanda:

"Quanti dati posso perdere?"

Esempio:



RPO 5 minuti


Significa:

massimo 5 minuti di dati persi.

---

# RTO

Recovery Time Objective.

Domanda:

"Quanto tempo posso stare fermo?"

Esempio:



RTO 30 minuti


---

# Networking Enterprise Example

Architettura completa:


              Internet

                 |

           Firewall HA

           /        \

      Router A     Router B

           |

      Core Switch HA

           |

    Spine / Leaf Network

           |

         Servers

           |

       Database Cluster


---

# Monitoraggio Alta Disponibilità

Controllare:

- stato link
- CPU
- memoria
- errori porte
- packet loss
- latenza

---

# Protocolli e strumenti

SNMP:



monitoraggio dispositivi


---

Syslog:



raccolta eventi


---

NetFlow:



analisi traffico


---

# Network Automation

Le reti moderne usano:

- API
- script
- Ansible
- Terraform

---

Esempio:

Invece di configurare:



100 switch manualmente


usi:



uno script


---

# Mentalità Enterprise

Una rete professionale deve essere:



Ridondante

Scalabile

Sicura

Monitorata

Automatizzata


---

# Concetto chiave

Ricorda:



HA

=

nessun punto singolo di guasto

Failover

=

passaggio automatico

LACP

=

più link insieme

HSRP/VRRP

=

gateway sempre disponibile

Spine-Leaf

=

data center moderno


---

# Fine Capitolo 22

Prossimo capitolo:

# 23 - Monitoraggio di rete e Network Operations Center (NOC)

Argomenti:

- come si controlla una rete reale 24/7
- SNMP
- Syslog
- NetFlow
- Prometheus
- Grafana
- alerting
- metriche fondamentali
- troubleshooting da NOC engineer

# 23 - Monitoraggio di rete e Network Operations Center (NOC)

Una rete professionale non deve solo funzionare.

Deve essere:



osservata

misurata

controllata

analizzata


Un network engineer bravo non aspetta che qualcuno dica:

"Internet è lento".

Lo sa prima.

---

# Cos'è un NOC?

NOC significa:



Network Operations Center


È il centro di controllo della rete.

Un NOC monitora:

- router
- switch
- firewall
- server
- cloud
- applicazioni
- collegamenti Internet

---

# Obiettivo del NOC

La domanda principale:



La rete sta bene?


Controlla:



Disponibilità

Prestazioni

Errori

Sicurezza


---

# Network Monitoring

Monitorare significa raccogliere dati.

Esempio:

Uno switch comunica:



CPU 40%

RAM 60%

Porta Gi0/1 traffico 700 Mbps

Errori 0


---

# Metriche fondamentali

Un network engineer guarda:

## Availability

Il dispositivo risponde?

---

## Latency

Quanto tempo impiega?

---

## Packet Loss

Quanti pacchetti vengono persi?

---

## Bandwidth

Quanto traffico passa?

---

## Errors

Ci sono problemi sulle porte?

---

# SNMP

Uno dei protocolli più importanti.

Significa:



Simple Network Management Protocol


Serve per:



monitorare dispositivi di rete


---

# Come funziona SNMP

Componenti:



Manager

Agent


---

# SNMP Manager

È il sistema di monitoraggio.

Esempi:

- server monitoring
- NMS

---

# SNMP Agent

È dentro il dispositivo.

Esempio:



Router

Switch

Firewall


---

Schema:



Monitoring Server

    |

  SNMP

    |


Router/Switch


---

# MIB

SNMP usa:



Management Information Base


È un database di informazioni.

Esempio:



CPU

Temperatura

Traffico porta

Errori


---

# OID

Ogni valore ha un identificatore.

Esempio:



OID

=
numero unico della metrica


---

# Versioni SNMP

## SNMPv1

Vecchio.

---

## SNMPv2c

Molto usato.

Usa:



community string


Problema:

non cifrata.

---

## SNMPv3

Versione sicura.

Supporta:

- autenticazione
- cifratura

---

# Esempio SNMP

Monitoring:

"Quanto traffico passa sulla porta?"

Chiede:



SNMP GET


Switch:



porta Gi0/1

500 Mbps


---

# Polling e Traps

Due modalità.

---

# Polling

Il monitoraggio chiede:



Come stai?


Esempio:

ogni:



60 secondi


---

# SNMP Trap

Il dispositivo avvisa.

Esempio:



Porta down!


---

# Syslog

Serve per raccogliere eventi.

Significa:



system logging


---

Esempio evento:



Firewall:

Tentativo login fallito


---

# Livelli Syslog

Dal più grave:



0 Emergency

1 Alert

2 Critical

3 Error

4 Warning

5 Notice

6 Informational

7 Debug


---

# Esempio Syslog

Router:



Interface GigabitEthernet0/1 DOWN


Invia:



Syslog Server


---

# NetFlow

Serve per capire:



chi usa la rete


Non guarda ogni pacchetto.

Guarda i flussi.

---

# Cos'è un Flow?

Una conversazione:



192.168.1.10

↓

8.8.8.8

TCP 443


---

# NetFlow mostra:

- IP sorgente
- IP destinazione
- porta
- protocollo
- quantità dati

---

# Esempio

Scopri:



PC interno

ha consumato

900 GB


---

# Utilità NetFlow

Trova:

- traffico anomalo
- macchine infette
- applicazioni pesanti
- problemi banda

---

# Packet Capture vs NetFlow

Wireshark:



vede pacchetti singoli


NetFlow:



vede conversazioni


---

# Dashboard NOC

Un NOC usa pannelli grafici.

Esempio:



Router Milano

CPU █████ 50%

Traffic ███████ 70%

Latency ███ 20ms

Status OK


---

# Zabbix

Sistema open source di monitoraggio.

Controlla:

- server
- rete
- applicazioni

---

# Prometheus

Molto usato nel cloud moderno.

Raccoglie:



metriche temporali


Esempio:

CPU:



09:00 40%

09:10 70%

09:20 90%


---

# Grafana

Visualizzazione dati.

Crea:

- dashboard
- grafici
- pannelli

---

# Stack moderno

Molte aziende usano:



Prometheus

Grafana

Alert Manager


---

# Alerting

Un sistema serio non guarda sempre manualmente.

Genera avvisi.

---

Esempio:

Regola:



CPU > 90%

per 5 minuti


Azione:



manda alert


---

# Tipi di Alert

## Warning

Problema possibile.

---

## Critical

Problema grave.

---

## Emergency

Servizio fermo.

---

# Monitoring SLA

Le aziende usano SLA:



Service Level Agreement


Esempio:

Disponibilità:



99.9%


---

# Baseline

Prima devi sapere:



cosa è normale


Esempio:

Traffico normale:



500 Mbps


Poi:



5 Gbps


è sospetto.

---

# Capacity Planning

Prevedere il futuro.

Domanda:

"La rete reggerà tra 6 mesi?"

Analizzare:

- crescita utenti
- crescita traffico
- nuovi servizi

---

# Interface Monitoring

Le porte switch sono fondamentali.

Controllare:

- stato
- velocità
- duplex
- errori

---

# Errori porta comuni

## CRC Errors

Possibili cause:

- cavo
- interferenze
- problemi hardware

---

## Drops

Pacchetti scartati.

Cause:

- congestione
- buffer pieno

---

## Collisions

Problema tipico reti vecchie.

---

# Monitoring Cloud

Nel cloud controlli:

- VM
- load balancer
- database
- firewall
- traffico

---

Metriche cloud:



CPU

Network In

Network Out

Latency

Requests

Errors


---

# Troubleshooting NOC

Metodo professionale:

---

## 1

Ricevi alert.

Esempio:



Server non raggiungibile


---

## 2

Verifica impatto.

Domanda:



Solo un utente?

Tutti?


---

## 3

Controlla livelli.



Fisico

↓

Data Link

↓

IP

↓

TCP

↓

Applicazione


---

## 4

Trova il punto di rottura.

---

# Esempio reale

Alert:



Web lento


Controllo:

DNS:

OK

TCP:

OK

Packet loss:

5%

Conclusione:



problema rete


---

# Network Monitoring Tools

Strumenti comuni:

- Wireshark
- tcpdump
- Zabbix
- Nagios
- Prometheus
- Grafana
- PRTG
- SolarWinds

---

# Network Operations Center Mentalità

Un NOC engineer pensa:



Cosa è cambiato?

Quando è iniziato?

Quanto è grande l'impatto?

Dove vedo il problema?

Quale dato lo dimostra?


---

# Concetto chiave

Ricorda:



SNMP

=

stato dispositivi

Syslog

=

eventi

NetFlow

=

chi usa la rete

Wireshark

=

analisi pacchetti

Grafana

=

visualizzazione

Alert

=

reazione automatica


---

# Fine Capitolo 23

Prossimo capitolo:

# 24 - Network Security: firewall, VPN, Zero Trust e difesa delle reti

Argomenti:

- firewall stateful
- IDS/IPS
- VPN
- IPsec
- SSL VPN
- Zero Trust
- segmentazione
- DMZ
- sicurezza cloud
- attacchi di rete e difese

# 24 - Network Security: firewall, VPN, Zero Trust e difesa delle reti

Una rete funzionante ma non protetta è una rete vulnerabile.

Un network engineer moderno deve sapere:



come far comunicare i sistemi

ma anche

come impedire comunicazioni pericolose


La sicurezza di rete non significa bloccare tutto.

Significa:



permettere ciò che serve

bloccare ciò che è rischioso


---

# Il modello della sicurezza di rete

Una rete sicura usa più livelli.

Questo concetto si chiama:



Defense in Depth


Difesa a strati.

---

Esempio:



Internet

|

Firewall

|

DMZ

|

Application Firewall

|

Server

|

Database


Se un livello viene superato:

gli altri proteggono.

---

# Firewall

Il firewall è il guardiano della rete.

Decide:



chi può entrare

chi può uscire

cosa può passare


---

# Firewall Layer 3/4

Controlla:

- IP
- porte
- protocolli

Esempio:

Permetti:



TCP 443


Blocca:



TCP 23


---

# Firewall Layer 7

Conosce le applicazioni.

Può controllare:

- HTTP
- URL
- contenuti
- utenti

---

Esempio:

Permette:



https://azienda.com


Blocca:



sito malevolo


---

# Packet Filtering Firewall

Il firewall analizza pacchetti.

Controlla:



IP sorgente

IP destinazione

porta

protocollo


---

Esempio regola:



ALLOW

Source:
10.0.0.0/24

Destination:
Web Server

Port:
443


---

# Stateful Firewall

Il firewall moderno è normalmente:



stateful


Significa:

ricorda le connessioni.

---

Esempio:

Client:



192.168.1.10

↓

Server HTTPS

443


Firewall registra:



connessione aperta


Quando torna la risposta:



permessa automaticamente


---

# Stateless Firewall

Non mantiene memoria.

Ogni pacchetto viene valutato singolarmente.

---

Problema:

Devi creare regole più complesse.

---

# NAT Firewall

Molti firewall fanno anche NAT.

Esempio:

Rete interna:



192.168.1.0/24


Internet vede:



IP pubblico


---

# DMZ

DMZ significa:



Demilitarized Zone


È una rete intermedia.

---

Serve per mettere:

- server web
- mail server
- servizi pubblici

---

Schema:



Internet

|

Firewall

|

DMZ

|

Firewall

|

LAN interna


---

# Perché DMZ?

Se un server pubblico viene compromesso:

non deve raggiungere direttamente:



rete aziendale interna


---

# ACL

Access Control List.

Sono regole di permesso/blocco.

---

Esempio router:



Permetti:

10.0.0.0/24

verso

Server


---

# IDS

Intrusion Detection System.

Rileva attività sospette.

---

Esempio:

Nota:



1000 tentativi SSH


Genera:



alert


---

# IPS

Intrusion Prevention System.

Fa un passo in più.

Non solo rileva.

Blocca.

---

Differenza:

IDS:



vede e avvisa


IPS:



vede e blocca


---

# Firewall vs IDS/IPS

Firewall:



controllo regole


IDS/IPS:



analisi comportamento


---

# VPN

VPN significa:



Virtual Private Network


Crea un collegamento sicuro sopra Internet.

---

Prima:



PC

|

Internet

|

Server


---

Dopo:



PC

|

Tunnel cifrato

|

Server


---

# Perché usare VPN?

Permette:

- accesso remoto
- collegamento sedi
- protezione traffico

---

# Tipi VPN

## Remote Access VPN

Utente singolo.

Esempio:

Dipendente da casa.

---

## Site-to-Site VPN

Collega reti.

Esempio:



Sede Milano

VPN

Sede Roma


---

# Tunnel VPN

Un tunnel crea:



canale virtuale cifrato


---

Dentro:



pacchetto originale


viene inserito:



dentro altro pacchetto


Questo processo:



encapsulation


---

# IPsec

Uno dei protocolli VPN più importanti.

Lavora a:



Layer 3


---

Componenti:

- Authentication Header (AH)
- Encapsulating Security Payload (ESP)

---

# ESP

È il più usato.

Fornisce:

- cifratura
- autenticazione
- integrità

---

# Encryption

Trasforma dati leggibili:



CIAO


in:



x7a9f2


---

Solo chi ha la chiave può leggere.

---

# AES

Algoritmo di cifratura molto usato.

Versioni:

- AES-128
- AES-256

---

# SSL VPN

VPN basata su TLS.

Spesso usata per:

- utenti remoti
- browser
- client aziendali

---

# WireGuard

VPN moderna.

Caratteristiche:

- semplice
- veloce
- codice ridotto

---

# Zero Trust

Modello moderno di sicurezza.

Principio:



Never trust, always verify


---

Significa:

Non fidarti automaticamente di:

- rete interna
- dispositivo
- utente

---

# Vecchio modello

Prima:



Dentro rete = sicuro

Fuori rete = pericoloso


---

# Zero Trust

Ora:



Ogni richiesta deve essere verificata


---

Controlla:

- identità
- dispositivo
- posizione
- autorizzazioni
- rischio

---

# Microsegmentazione

Dividere la rete in piccoli segmenti.

---

Prima:



Grande LAN

Tutti parlano con tutti


---

Dopo:



Utenti

|

Applicazioni

|

Database


---

Ogni zona ha regole.

---

# VLAN Security

Le VLAN separano reti.

Esempio:



VLAN 10

Utenti

VLAN 20

Server

VLAN 30

Guest


---

Un utente guest non deve vedere server interni.

---

# Network Access Control (NAC)

Controlla chi entra nella rete.

Esempio:

Un PC collega cavo.

NAC controlla:

- antivirus
- aggiornamenti
- autorizzazioni

---

# Authentication

Identificare utenti.

Metodi:

- password
- certificati
- MFA

---

# MFA

Multi Factor Authentication.

Usa più fattori:



qualcosa che sai

qualcosa che possiedi

qualcosa che sei


---

Esempio:

Password:

+

app autenticatore.

---

# AAA

Tre concetti fondamentali:



Authentication

Authorization

Accounting


---

## Authentication

Chi sei?

---

## Authorization

Cosa puoi fare?

---

## Accounting

Cosa hai fatto?

---

# RADIUS

Protocollo AAA molto usato.

Usato per:

- WiFi aziendale
- VPN
- accesso rete

---

# TACACS+

Usato spesso in ambienti Cisco.

Permette controllo dettagliato comandi amministrativi.

---

# Attacchi di rete comuni

---

# DDoS

Distributed Denial of Service.

Obiettivo:

saturare un servizio.

---

Schema:



Migliaia di computer

    |

    |

 Server


---

Difese:

- rate limiting
- CDN
- scrubbing
- firewall cloud

---

# Port Scanning

Un attaccante cerca:



porte aperte


---

Esempio:



22 SSH

80 HTTP

443 HTTPS


---

Difesa:

- chiudere porte inutili
- firewall
- monitoraggio

---

# Man in the Middle

Attaccante intercetta comunicazione.

---

Difese:

- cifratura
- certificati
- VPN

---

# ARP Spoofing

Attacco nella LAN.

L'attaccante falsifica associazioni:



IP

MAC


---

Difese:

- Dynamic ARP Inspection
- segmentazione
- sicurezza switch

---

# DNS Attack

Attacchi al sistema DNS.

Esempio:

mandare utenti verso siti falsi.

---

Difese:

- DNSSEC
- DNS filtering
- monitoraggio

---

# TLS / HTTPS

Protegge traffico web.

Processo:



Client

|

TLS Handshake

|

Chiavi

|

Traffico cifrato


---

# Certificati Digitali

Dimostrano:



chi è il server


---

Esempio:

Browser controlla:



Questo certificato appartiene davvero al sito?


---

# Security Logging

Una rete sicura registra:

- login
- errori
- firewall block
- accessi VPN

---

# SIEM

Security Information and Event Management.

Raccoglie:



log da tutta l'infrastruttura


---

Esempio:

Firewall:



login fallito


Server:



utente sospetto


SIEM:



crea evento sicurezza


---

# Sicurezza Cloud

Nel cloud vale:



Shared Responsibility Model


---

Il provider protegge:

- infrastruttura fisica
- hardware
- rete base

---

Il cliente protegge:

- configurazioni
- utenti
- firewall
- dati

---

# Security Group Cloud

Firewall virtuale.

Controlla:

- ingress
- egress
- porte
- IP

---

# Bastion Host

Punto controllato per accesso amministrativo.

Schema:



Internet

|

Bastion

|

Server privati


---

# Hardening di rete

Rendere un sistema più sicuro.

Include:

- chiudere porte inutili
- aggiornamenti
- password forti
- MFA
- logging
- backup configurazioni

---

# Network Security Checklist

Controllare:



Firewall configurato?

Porte inutili chiuse?

VPN sicura?

MFA attivo?

Log raccolti?

Segmentazione presente?

Backup disponibili?

Aggiornamenti applicati?


---

# Mentalità Security Engineer

Non pensare:

"Come entro?"

Pensa:



Cosa devo proteggere?

Chi deve accedere?

Quale rischio esiste?

Come posso limitarlo?


---

# Concetto chiave

Ricorda:



Firewall

=
controllo traffico

VPN

=
tunnel cifrato

IDS

=
rileva

IPS

=
blocca

Zero Trust

=
verifica sempre

DMZ

=
zona isolata per servizi pubblici


---

# Fine Capitolo 24

Prossimo capitolo:

# 25 - Linux Networking da amministratore professionista

Argomenti:

- configurazione rete Linux
- ip command
- routing Linux
- firewall nftables/iptables
- DNS Linux
- SSH avanzato
- socket
- porte
- troubleshooting completo
- gestione server reale

# 25 - Linux Networking da amministratore professionista

Linux è il sistema operativo più usato nei server.

Lo trovi in:

- cloud
- data center
- router
- firewall
- container
- Kubernetes
- sistemi embedded

Un network engineer deve sapere amministrare Linux dalla riga di comando.

---

# Filosofia Linux Networking

Linux vede la rete come:



interfacce

indirizzi IP

routing

servizi

socket


Tutto è controllabile tramite:



terminal


---

# Identificare le interfacce di rete

Comando moderno:

```bash
ip addr


Esempio:

eth0

inet 192.168.1.50/24


Significa:

interfaccia:

eth0


IP:

192.168.1.50


rete:

/24

Interfacce comuni Linux
Ethernet
eth0


oppure:

ens33

WiFi
wlan0

Loopback
lo


Indirizzo:

127.0.0.1

Stato interfaccia

Vedere interfacce:

ip link


Esempio:

state UP


oppure:

state DOWN

Attivare interfaccia
sudo ip link set eth0 up

Disattivare
sudo ip link set eth0 down

Configurare IP temporaneo

Esempio:

sudo ip addr add 192.168.1.100/24 dev eth0

Rimuovere IP
sudo ip addr del 192.168.1.100/24 dev eth0

Gateway predefinito

Visualizzare:

ip route


Esempio:

default via 192.168.1.1


Significa:

tutto il traffico sconosciuto va al router.

Aggiungere route
sudo ip route add 10.10.0.0/16 via 192.168.1.1

Eliminare route
sudo ip route del 10.10.0.0/16

Test rete base
Ping
ping 8.8.8.8


Controlla:

connettività IP

Ping gateway
ping 192.168.1.1


Se fallisce:

problema locale.

Traceroute

Installazione:

sudo apt install traceroute


Uso:

traceroute google.com


Mostra:

PC

↓

Router

↓

ISP

↓

Destinazione

DNS Linux

DNS traduce:

nome

↓

IP


Esempio:

google.com

↓

142.x.x.x

Test DNS
nslookup google.com


oppure:

dig google.com

File DNS principali
resolv.conf
/etc/resolv.conf


Contiene:

nameserver


Esempio:

nameserver 8.8.8.8

Host locali

File:

/etc/hosts


Permette associazioni manuali.

Esempio:

192.168.1.20 server1

Ordine risoluzione nomi

Linux controlla:

/etc/hosts

↓

DNS

↓

altro


Configurato in:

/etc/nsswitch.conf

Porte Linux

Ogni servizio ascolta su una porta.

Esempi:

SSH

22


HTTP

80


HTTPS

443


DNS

53

Vedere porte aperte

Comando moderno:

ss -tulnp


Esempio:

LISTEN

0.0.0.0:22

sshd


Significa:

SSH attivo.

Netstat

Vecchio comando:

netstat -tulnp


Oggi si preferisce:

ss

Socket

Un socket identifica:

IP

+

porta

+

protocollo


Esempio:

192.168.1.10:50000

↓

8.8.8.8:443

Connessioni attive
ss -tun


Mostra:

TCP
UDP
connessioni
SSH

Secure Shell.

Serve per amministrare server remoti.

Schema:

PC

 |

SSH cifrato

 |

Server Linux

Connessione SSH
ssh user@server_ip


Esempio:

ssh admin@192.168.1.50

Porte SSH

Default:

22


Cambiare porta:

File:

/etc/ssh/sshd_config


Parametro:

Port 2222

Chiavi SSH

Metodo professionale.

Coppia:

chiave privata

+

chiave pubblica


Generare:

ssh-keygen


Copiare chiave:

ssh-copy-id user@server

Sicurezza SSH

Buone pratiche:

disabilitare root login
usare chiavi
usare MFA
limitare IP
aggiornare
Firewall Linux

Linux usa firewall nel kernel.

Tecnologie:

iptables
nftables
ufw
UFW

Firewall semplice Ubuntu.

Stato:

sudo ufw status


Attivare:

sudo ufw enable


Permettere SSH:

sudo ufw allow 22


Permettere HTTPS:

sudo ufw allow 443


Bloccare porta:

sudo ufw deny 23

Regole firewall

Esempio:

Permetti:

TCP 80


Blocca:

TCP 23

nftables

Successore moderno di iptables.

Architettura:

Network Packet

↓

nftables rules

↓

Accetta o blocca

Packet Flow Linux

Quando arriva un pacchetto:

Scheda rete

↓

Kernel

↓

Firewall

↓

Routing

↓

Applicazione

iptables concetto

Catene principali:

INPUT

OUTPUT

FORWARD


INPUT:

Traffico verso il server.

OUTPUT:

Traffico generato dal server.

FORWARD:

Traffico instradato.

Linux come Router

Linux può fare routing.

Abilitare:

File:

/etc/sysctl.conf


Parametro:

net.ipv4.ip_forward=1


Applicare:

sudo sysctl -p


Ora Linux può:

ricevere pacchetti

e inoltrarli

NAT Linux

Usato per condividere Internet.

Esempio:

LAN privata

192.168.1.0/24

↓

Linux Router

↓

Internet

NetworkManager

Gestisce connessioni Linux moderne.

Comandi:

nmcli


Vedere connessioni:

nmcli connection show


Vedere dispositivi:

nmcli device status

Systemd Network

Alcuni server usano:

systemd-networkd

DHCP Client

Ottenere IP automaticamente:

dhclient eth0

Informazioni hardware rete

PCI:

lspci | grep network


Interfacce:

ethtool eth0


Mostra:

velocità
duplex
stato link
Velocità scheda

Esempio:

Speed:

1000Mb/s

Duplex

Full duplex:

trasmissione e ricezione contemporanee


Half duplex:

un senso alla volta

ARP Linux

Visualizzare tabella:

ip neigh


Esempio:

192.168.1.1

aa:bb:cc:dd

Packet Capture Linux

Strumento:

tcpdump


Catturare tutto:

sudo tcpdump


Interfaccia:

sudo tcpdump -i eth0


Salvare:

sudo tcpdump -w traffico.pcap


Leggere:

tcpdump -r traffico.pcap

Filtri tcpdump

Solo host:

tcpdump host 8.8.8.8


Solo porta:

tcpdump port 443


Solo TCP:

tcpdump tcp

Diagnosi rete completa

Metodo professionale:

1

Controlla interfaccia:

ip addr

2

Controlla route:

ip route

3

Controlla DNS:

dig dominio.com

4

Controlla porte:

ss -tulnp

5

Controlla firewall:

ufw status

6

Analizza pacchetti:

tcpdump

Log di rete Linux

Directory:

/var/log


Log importanti:

syslog

auth.log

kern.log

Journald

Sistema moderno:

journalctl


Vedere errori:

journalctl -p err


Seguire log:

journalctl -f

Servizi di rete Linux

Vedere servizi:

systemctl list-units


SSH:

systemctl status ssh


Riavviare:

sudo systemctl restart ssh

Server Web Linux

Esempio:

Nginx.

Porta:

80

443


Controllare:

ss -tulnp | grep nginx

Reverse Proxy

Schema:

Internet

↓

Nginx

↓

Applicazione


Usato per:

sicurezza
SSL
bilanciamento
Linux Networking Mental Model

Quando qualcosa non funziona:

segui il percorso:

Hardware

↓

Interfaccia

↓

IP

↓

Route

↓

Firewall

↓

Porta

↓

Servizio

↓

Applicazione

Concetto chiave

Ricorda:

ip addr

=

indirizzi


ip route

=

percorsi


ss

=

porte e connessioni


tcpdump

=

pacchetti


ufw/nftables

=

sicurezza


ssh

=

amministrazione remota

Fine Capitolo 25

Prossimo capitolo:

26 - Automazione Networking: Python, API, Ansible e infrastruttura come codice

Argomenti:

perché il network engineer deve programmare
Python per networking
REST API
JSON
automazione switch/router
Ansible
Terraform
DevNet
NetOps moderno

# 26 - Automazione Networking: Python, API, Ansible e Infrastructure as Code

Il network engineer moderno non configura più tutto manualmente.

La rete di oggi può avere:

- migliaia di switch
- centinaia di firewall
- migliaia di server
- infrastrutture cloud enormi

Fare tutto a mano significa:

- errori
- lentezza
- impossibilità di scalare

La soluzione:



automazione


---

# Il vecchio Network Engineer

Prima:



Apri terminale

SSH allo switch

Scrivi comandi

Ripeti 500 volte


---

# Il Network Engineer moderno

Oggi:



Scrive codice

Definisce configurazione

La applica automaticamente


---

# NetOps

Nuovo approccio:



Network

Operations

Automation


Si chiama:



NetOps


---

# Perché programmare una rete?

Esempio:

Devi creare VLAN su:



300 switch


Manualmente:

ore o giorni.

Con automazione:



uno script

↓

300 dispositivi


---

# Concetto fondamentale

Una rete diventa:



programmabile


---

# API

API significa:



Application Programming Interface


Permette a due sistemi di comunicare.

---

Esempio:

Prima:



Umano

↓

CLI Router


Dopo:



Script

↓

API Router


---

# REST API

Il tipo più comune.

Usa:



HTTP


---

Metodi principali:

## GET

Leggere dati.

Esempio:



Dammi configurazione


---

## POST

Creare qualcosa.

Esempio:



Crea VLAN


---

## PUT

Modificare.

---

## DELETE

Eliminare.

---

# JSON

Le API usano spesso JSON.

Esempio:

```json
{
 "interface": "eth0",
 "ip": "192.168.1.10"
}


JSON è:

testo strutturato


facile da leggere per macchine.

Python per Networking

Python è il linguaggio più usato.

Perché:

semplice
potente
molte librerie
ottimo per API
Primo script Python
print("Network Engineer")

Variabili
ip = "192.168.1.10"

print(ip)

Liste

Esempio:

switches = [
"switch1",
"switch2",
"switch3"
]

Cicli

Ripetere operazioni:

for switch in switches:
    print(switch)


Risultato:

switch1
switch2
switch3

Condizioni
if ping == True:
    print("Online")
else:
    print("Offline")

Ping automatico

Esempio concettuale:

import os

os.system("ping 8.8.8.8")

Libreria Requests

Serve per chiamare API.

Installazione:

pip install requests


Esempio:

import requests

response = requests.get(
"https://api.example.com"
)

print(response.text)

SSH automatico con Python

Libreria:

paramiko


Installazione:

pip install paramiko


Permette:

Python

↓

SSH

↓

Router

Netmiko

Libreria specializzata networking.

Supporta:

Cisco
Arista
Juniper
Linux

Installazione:

pip install netmiko


Esempio concettuale:

from netmiko import ConnectHandler

device = {
"device_type":"cisco_ios",
"host":"192.168.1.1",
"username":"admin",
"password":"password"
}


Poi:

connection.send_command(
"show ip interface brief"
)

NAPALM

Network Automation and Programmability Abstraction Layer with Multivendor support.

Permette stesso codice per:

Cisco
Juniper
Arista
YAML

Molto usato nell'automazione.

Esempio:

device:
  name: router1
  ip: 10.0.0.1

Ansible

Uno degli strumenti più importanti.

È:

automazione senza agent


Funziona:

Ansible Controller

        |

        |

Router/Switch/Linux

Perché Ansible?

Permette:

configurazioni
aggiornamenti
deploy
gestione massa
Inventory Ansible

Elenco dispositivi.

Esempio:

[routers]

router1

router2

Playbook

File YAML che descrive cosa fare.

Esempio:

- name: Configure VLAN
  hosts: switches

  tasks:

  - name:
      Create VLAN

Concetto Ansible

Non dici:

esegui questi 20 comandi


Dici:

voglio questo stato finale


Questo si chiama:

idempotenza

Idempotenza

Esempio:

Prima esecuzione:

crea VLAN 10


Seconda:

VLAN già presente


Non rompe nulla.

Terraform

Strumento Infrastructure as Code.

Molto usato nel cloud.

Permette creare:

reti
server
firewall
database

tramite codice.

Esempio:

Invece di:

cliccare 100 volte nel pannello cloud


scrivi:

file Terraform

Infrastructure as Code (IaC)

Concetto:

La configurazione diventa:

codice versionato


Vantaggi:

ripetibilità
controllo versioni
collaborazione
meno errori
Git

Fondamentale.

Serve per:

versionare codice
collaborare
tornare indietro

Comandi base:

git init


Aggiungere:

git add .


Commit:

git commit -m "network change"

CI/CD per Networking

Concetto preso dallo sviluppo software.

Schema:

Modifica codice

↓

Test

↓

Approvazione

↓

Deploy rete

GitOps

Approccio moderno:

La rete è descritta in Git.

Esempio:

Git Repository

        |

        |

Automazione

        |

        |

Infrastruttura

SDN

Software Defined Networking.

Cambiare modello:

Prima:

Ogni router decide


Dopo:

Controller centrale

SDN Architecture

Tre livelli:

Application Layer

        |

Control Layer

        |

Infrastructure Layer

Control Plane e Data Plane

Ricorda:

Router normale:

Control Plane

decide


Data Plane

inoltra pacchetti


SDN separa:

Decisione

da

Inoltro

Network Controller

Esempio:

Controller decide:

crea VLAN

sposta traffico

applica policy

Intent Based Networking

La rete capisce l'obiettivo.

Esempio:

Tu dici:

Server database deve essere isolato


Il sistema crea:

VLAN
firewall rules
policy
Automazione Cloud

Cloud usa API ovunque.

Esempi:

Creare:

VPC

Subnet

Firewall

VM


tramite codice.

Container Networking

Con Docker e Kubernetes.

Concetti:

bridge
overlay network
service
ingress
Kubernetes Networking

Ogni container riceve:

IP


I servizi comunicano tramite:

Service

Monitoring Automatico

Uno script può controllare:

CPU

RAM

latenza

packet loss


e creare:

alert automatici

Esempio progetto reale

Obiettivo:

Configurare 100 switch.

Processo:

File YAML

↓

Ansible

↓

SSH/API

↓

Switch

↓

Configurazione applicata

Sicurezza Automazione

Mai mettere:

password dentro codice.

Usare:

Vault
Secret Manager
chiavi SSH
Network Engineer del futuro

Deve conoscere:

Networking

+

Linux

+

Python

+

API

+

Cloud

+

Automation

Skill fondamentali

Livello Junior:

IP
subnetting
VLAN
TCP/IP

Livello Mid:

routing
firewall
VPN
Linux

Livello Senior:

automazione
cloud
architetture
sicurezza
Mentalità DevNet

Non pensare:

"configuro un dispositivo"

Pensa:

"gestisco un'infrastruttura programmabile"

Concetto chiave

Ricorda:

API

=
comunicazione software


Python

=
automazione


Ansible

=
configurazione massa


Terraform

=
infrastruttura come codice


Git

=
versionamento


SDN

=
rete controllata dal software

Fine Capitolo 26

Prossimo capitolo:

27 - Cloud Networking: AWS, Azure, OCI e reti moderne

Argomenti:

VPC
subnet cloud
security group
load balancer
NAT Gateway
Internet Gateway
VPN cloud
peering
cloud architecture
Oracle Cloud Free Tier networking

# 27 - Cloud Networking: AWS, Azure, OCI e reti moderne

Il cloud ha cambiato il modo di costruire reti.

Prima:



Server fisici

↓

Switch fisici

↓

Router fisici


Oggi:



Codice

↓

Rete virtuale

↓

Risorse cloud


Un network engineer moderno deve capire:

- reti virtuali
- routing cloud
- sicurezza cloud
- connessioni ibride
- automazione

---

# Cos'è il Cloud Networking?

È la progettazione di reti dentro un provider cloud.

I principali provider:

- AWS
- Microsoft Azure
- Oracle Cloud Infrastructure (OCI)
- Google Cloud

---

# La rete cloud è virtuale

Nel cloud non compri:



uno switch fisico


Crei:



uno switch virtuale


Non configuri:



un router fisico


Crei:



routing virtuale


---

# Modello mentale Cloud

Pensa così:



Data Center Provider

    |


Virtualizzazione

    |


La tua rete privata


---

# VPC / VCN

Ogni cloud ha un concetto simile.

AWS:



VPC


Azure:



Virtual Network


OCI:



VCN


---

Sono una:



rete privata virtuale isolata


---

# Esempio VCN OCI



VCN

10.0.0.0/16

    |

    |


| |

Subnet Pubblica Subnet Privata

10.0.1.0/24 10.0.2.0/24


---

# CIDR nel Cloud

Ogni rete deve avere un intervallo IP.

Esempio:



10.0.0.0/16


Contiene:



65536 indirizzi


---

Subnet:



10.0.1.0/24


Contiene:



256 indirizzi


---

# Subnet Pubbliche

Una subnet pubblica può comunicare direttamente con Internet.

Tipico uso:

- web server
- load balancer
- bastion host

---

Schema:



Internet

|

Gateway Internet

|

Subnet Pubblica

|

Server Web


---

# Subnet Private

Non hanno accesso diretto da Internet.

Usate per:

- database
- applicazioni interne
- servizi sensibili

---

Schema:



Internet

|

Firewall

|

Application Server

|

Database Privato


---

# Internet Gateway

Permette comunicazione:



Cloud

↓

Internet


---

Esempio:

Un web server pubblico riceve:



HTTP 443


attraverso Internet Gateway.

---

# NAT Gateway

Serve al contrario.

Permette ai server privati di uscire su Internet.

Esempio:

Server database:



10.0.2.50


deve scaricare aggiornamenti.

Usa:



NAT Gateway


---

Schema:



Server Privato

10.0.2.50

  |


NAT Gateway

  |


Internet


---

# Route Table Cloud

Come nei router normali.

Decide:



dove mandare il traffico


---

Esempio:



Destinazione Target

10.0.0.0/16 locale

0.0.0.0/0 Internet Gateway


---

# Security Group

Firewall virtuale.

Controlla:

- ingress
- egress
- porte
- protocolli

---

Esempio:

Permetti:



TCP 443

da Internet


Blocca:



TCP 22


---

# Network ACL

Un altro livello firewall.

Differenza:

Security Group:



livello macchina


Network ACL:



livello subnet


---

# Stateful e Stateless

Security Group:



stateful


Ricorda connessioni.

---

Network ACL:



stateless


Ogni pacchetto viene valutato.

---

# Load Balancer Cloud

Distribuisce traffico.

Schema:



Utenti

|

Load Balancer

/ | \

VM1 VM2 VM3


---

Tipi:

## Layer 4

TCP/UDP

---

## Layer 7

HTTP/HTTPS

---

# Auto Scaling

Il cloud può creare server automaticamente.

Esempio:

Traffico normale:



3 server


Picco:



20 server


---

# Elasticità

Differenza importante:

Scalabilità:



aggiungere risorse


Elasticità:



aggiungere e togliere automaticamente


---

# Cloud DNS

Il DNS nel cloud collega:



nome

↓

risorsa cloud


---

Esempio:



app.miosito.com

↓

Load Balancer


---

# Private DNS

Serve per reti interne.

Esempio:



database.internal


raggiungibile solo dentro VCN.

---

# Peering

Collega due reti private.

Esempio:



VCN Azienda A

    |

 Peering

    |


VCN Azienda B


---

# Transit Gateway

Per molte reti.

Problema:

100 VPC.

Non vuoi creare:



4950 collegamenti


---

Soluzione:



Transit Gateway


---

Schema:


    VPC1

      |


VPC2 -- Transit -- VPC3

      |

    VPC4


---

# VPN Cloud

Collega:



rete aziendale

    |


VPN

    |


Cloud


---

Esempio:

Ufficio:



192.168.1.0/24


Cloud:



10.0.0.0/16


---

# Site-to-Site VPN

Connette due reti.

Usa spesso:

- IPsec
- IKE
- cifratura

---

# Direct Connect / FastConnect

Connessione privata dedicata.

Esempio:

Azienda:



Data Center

  |


Fibra privata

  |


Cloud


---

Vantaggi:

- latenza bassa
- banda garantita
- maggiore stabilità

---

# Cloud Routing

I cloud hanno router virtuali.

Gestiscono:

- route interne
- Internet
- VPN
- peering

---

# BGP nel Cloud

Molte VPN enterprise usano BGP.

Esempio:



Router aziendale

    |

   BGP

    |


Cloud Router


---

# OCI Networking (Oracle Cloud)

Oracle Cloud usa:



VCN


---

Componenti principali:



VCN

Subnet

Route Table

Security List

NSG

Internet Gateway

NAT Gateway

DRG


---

# Dynamic Routing Gateway (DRG)

È il collegamento verso reti esterne.

Serve per:

- VPN
- FastConnect
- reti ibride

---

Schema:



Rete Aziendale

  |

  |

 DRG

  |

 VCN


---

# Oracle Cloud Free Tier Networking

Una macchina Free Tier tipica:



Internet

|


Public IP

|


VCN

|


Subnet

|


Compute Instance


---

Per amministrarla:



SSH porta 22


---

# Sicurezza VM Cloud

Regole fondamentali:

Mai aprire:



0.0.0.0/0

porta 22


senza motivo.

Meglio:



solo tuo IP


---

# Bastion Host Cloud

Accesso controllato.

Schema:



Internet

|

Bastion

|

Server Privati


---

# Cloud Firewall Mentalità

Regola:



nega tutto

permetti solo necessario


---

Esempio:

Web Server:

Permetti:



443 Internet


SSH:



solo amministratore


Database:



solo Application Server


---

# Architettura Cloud Professionale

Esempio:


             Internet

                |

          Load Balancer

                |

          Web Subnet

                |

        Application Subnet

                |

         Database Subnet


          VPN / DRG

                |

         Rete Aziendale


---

# Monitoring Cloud

Controllare:

- CPU
- RAM
- traffico
- errori
- latency
- connessioni

---

# Cloud Logging

Raccoglie:

- accessi
- firewall
- API
- eventi sicurezza

---

# Cloud Security Best Practice

Sempre:



MFA

IAM corretto

Least Privilege

Backup

Logging

Encryption

Network Segmentation


---

# IAM

Identity and Access Management.

Gestisce:



chi può fare cosa


---

Esempio:

Utente:



può leggere server

ma non cancellarli


---

# Least Privilege

Principio:

Dare:



solo permessi necessari


---

# Shared Responsibility Model

Fondamentale.

Provider protegge:



hardware

data center

infrastruttura fisica


---

Cliente protegge:



configurazioni

account

dati

firewall

permessi


---

# Hybrid Cloud

Unisce:



Cloud

On Premise


---

Esempio:



Azienda

|

VPN

|

Cloud


---

# Multi Cloud

Usare più provider.

Esempio:



AWS

OCI

Azure


---

Motivi:

- resilienza
- costi
- esigenze tecniche

---

# Cloud Network Engineer Skill

Deve sapere:



TCP/IP

Subnetting

Routing

Firewall

Linux

Python

API

Terraform

Cloud Architecture


---

# Mentalità Cloud

Non pensare:

"Ho un server"

Pensa:

"Ho un'infrastruttura programmabile"

---

# Concetto chiave

Ricorda:



VPC/VCN

=
rete privata cloud

Subnet

=
segmentazione rete

Route Table

=
decisioni traffico

Security Group

=
firewall macchina

NAT Gateway

=
uscita Internet privata

Load Balancer

=
distribuzione traffico

VPN

=
collegamento sicuro

BGP

=
routing dinamico cloud


---

# Fine Capitolo 27

Prossimo capitolo:

# 28 - Container Networking e Kubernetes: la rete dei moderni data center

Argomenti:

- Docker networking
- bridge network
- overlay network
- Kubernetes CNI
- pod
- service
- ingress
- load balancing
- service mesh
- networking cloud native
