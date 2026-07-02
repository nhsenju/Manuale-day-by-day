# Windows, WSL, VS Code, Docker — Guida semplice

*Spiegazione per principianti assoluti, letta in circa 15 minuti.*

## L'idea generale

Immagina di dover cucinare in tante cucine diverse (il tuo computer, quello di un collega, un server in azienda) e vuoi che la ricetta venga **sempre identica**, senza sorprese.

Questi 4 strumenti servono esattamente a questo: creare un ambiente di lavoro controllato e riproducibile per scrivere e far funzionare codice.

---

## 1. Windows — la casa

Windows è il **sistema operativo**: il "motore" che fa funzionare il computer (schermo, mouse, file, internet). È **la casa** in cui vivi. Comoda e familiare, ma pensata per uso generico (email, film, giochi), non per lo sviluppo software professionale.

## 2. WSL — una stanza speciale dentro casa, con impianti diversi

Molti programmi da sviluppatore sono pensati per **Linux**, un altro sistema operativo, usatissimo nei server di tutto il mondo. Tu però hai Windows, non Linux.

**WSL (Windows Subsystem for Linux)** è come costruire dentro casa tua (Windows) **una stanza con impianti idraulici ed elettrici diversi** (quelli di Linux, versione "Ubuntu"). Puoi usare gli attrezzi da "cucina Linux" senza comprare una casa nuova, cioè senza formattare il PC.

Dentro questa stanza lavori con il **terminale**: una finestra dove non clicchi col mouse, ma scrivi comandi a parole (come dare ordini per iscritto invece che a gesti). Sembra vecchio stile, ma è il modo più diretto e potente di parlare al computer.

**Perché esiste:** tanti strumenti di programmazione funzionano meglio, più velocemente, o *solo* su Linux. WSL evita di dover avere due computer fisici diversi.

## 3. Visual Studio Code (VS Code) — il banco da lavoro

VS Code è un **editor di codice**: il tavolo da lavoro dove scrivi le tue "ricette" (il codice). Evidenzia gli errori, suggerisce completamenti, organizza i file.

La cosa furba: VS Code sta "fisicamente" su Windows (ci clicchi sopra normalmente), ma può **allungare un braccio dentro la stanza WSL** e lavorare come se fosse lì. Comodità dell'interfaccia Windows, ma il codice viene eseguito davvero nell'ambiente Linux.

## 4. Docker — scatole pre-confezionate con tutto l'occorrente

Immagina dei **kit pasto pronti**: dentro ogni scatola c'è già tutto — ingredienti, pentole, istruzioni — così chiunque la apra, in qualsiasi cucina del mondo, ottiene lo stesso piatto.

Queste scatole si chiamano **container**. Un container è un "pacchetto" che contiene un programma **più tutto ciò che gli serve per funzionare** (altri programmi di supporto, impostazioni, versioni specifiche). È più leggero di una "macchina virtuale" intera: usa l'impianto del sistema ospite, ma tiene tutto il resto isolato e impacchettato.

**Docker** è lo strumento che crea, apre e gestisce queste scatole. Vantaggio enorme: se il progetto funziona nel container, funziona **identico** ovunque — sul PC del collega, su un server aziendale — perché la scatola è sempre la stessa.

---

## Come lavorano insieme, in pratica

1. **Windows** ospita tutto (è la casa).
2. Dentro Windows, **WSL** dà una stanza "Linux" con un terminale adatto allo sviluppo.
3. **VS Code** è il tavolo su cui scrivi il codice, collegato dentro quella stanza WSL.
4. **Docker** (collegato a WSL) impacchetta il progetto e le sue dipendenze in una scatola (container) che gira nella stessa stanza Linux.

Risultato: scrivi comodamente da Windows, ma tutto ciò che conta — l'esecuzione vera del codice — avviene in un ambiente Linux pulito e, con Docker, dentro una scatola isolata e riproducibile.

---

## Dietro le quinte: cosa succede quando scrivi ed esegui codice

1. Apri VS Code su Windows → clicchi.
2. VS Code si collega alla stanza WSL (Linux) → trova lì i file del progetto.
3. Scrivi il codice nell'editor (il banco da lavoro).
4. Premi "esegui" → il comando parte nel terminale, dentro WSL.
5. Se il progetto usa Docker, quel comando dice a Docker: "apri la scatola (container) e fai partire quello che c'è dentro".
6. Docker prepara l'ambiente isolato (le "pentole e ingredienti" giusti) e fa girare il programma.
7. Il risultato (es. un sito web che parte, un test che passa) torna indietro e lo vedi nel terminale o nel browser su Windows.

Tu vedi solo "ho premuto un bottone ed è partito", ma sotto ci sono questi passaggi a catena.

---

## Perché non fare tutto direttamente su Windows?

- **Compatibilità**: molti strumenti sono fatti per Linux; su Windows puro danno problemi o si comportano diversamente.
- **Coerenza**: senza Docker, ogni computer ha versioni diverse di programmi installati → "sul mio PC funziona, sul tuo no". Con Docker, la scatola è identica ovunque.
- **Ordine**: invece di installare mille programmi sparsi su Windows (con rischio di conflitti tra versioni), tieni tutto isolato e pulito, a compartimenti.

Sono soluzioni al **caos**: ambienti diversi, versioni diverse, "funziona solo sul mio computer" — problemi classici dello sviluppo software.

---

## Esempio pratico passo-passo

Apri un progetto già pronto (es. scaricato da GitHub):

1. Apri VS Code su Windows.
2. VS Code si collega alla stanza WSL dove sta il progetto.
3. Vedi i file del progetto nel pannello a sinistra (li modifichi come faresti su Word, ma per codice).
4. Apri il terminale integrato in VS Code (in realtà è il terminale Linux di WSL).
5. Scrivi un comando tipo `docker compose up` → Docker legge un "elenco della spesa" (file di configurazione) che dice quali scatole servono: magari una per il sito web, una per il database.
6. Docker scarica/prepara quelle scatole e le avvia.
7. Apri il browser su Windows, vai su `localhost:3000` (indirizzo che punta al computer stesso) e vedi il progetto funzionare, esattamente come funzionerebbe su qualsiasi altro computer con lo stesso setup.

---

## Riassunto in 5 righe

Windows è la casa dove vivi. WSL è una stanza dentro casa con gli impianti di Linux, necessari per lavorare bene da sviluppatore. VS Code è il banco da lavoro dove scrivi il codice, collegato a quella stanza. Docker crea scatole pre-confezionate (container) con tutto ciò che serve al progetto, così funziona identico ovunque. Insieme: scrivi comodo su Windows, ma esegui tutto in un ambiente Linux pulito e riproducibile.

## Analogia unica da ricordare

> Sei uno chef (tu) in casa tua (Windows). Hai costruito una cucina professionale extra (WSL) perché le ricette migliori si fanno lì. Il tuo banco da lavoro con tutti gli attrezzi in ordine è VS Code. Docker è il tuo sistema di kit pasto sottovuoto: ogni ricetta viene chiusa in una confezione con tutto dentro, così puoi spedirla a chiunque, ovunque, e verrà sempre identica.
