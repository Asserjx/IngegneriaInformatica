# Domande orali di Reti Informatiche
<div align="center">
Di seguito è presente una lista di domande poste dai professori G. Anastasi e F. Pistolesi durante gli esami di Reti Informatiche.
<br>
<b>aggiornato al:</b> <i>02/11/2022</i>
</div>
<details>
  <summary>Credits</summary>
  <i>Hanno contribuito:<br>
  	 <ul> 
	 	<li>M. Lampis</li>
	 </ul>
  </i>
</details>


| Simbolo | priorità 
| --- | --       	 
| 🟥  | Massimà 	
| 🟧  | Alta		
| 🟨  | Media		
| 🟩  | Bassa


---

## Domande Anastasi

- Sistema DNS


- http

- web caching


### Applicazioni di rete
- 🟥 **CS** e **P2P**:
  - differenze, pro e contro
  - esempio file grande F, calcolare l'asintoto orizzontale nel caso P2P
  - In che senso noi intendiamo che un dispositivo può essere client o server? (Un dispositivo si dice che è server se in esso gira il processo server)
  - I peer devono essere sempre attivi? (NO)
  - È più vantaggioso utilizzare un approccio client-server o peer to peer per inviare un file? Qual è l’istante iniziale?(Quando il file viene messo a disposizione). E l’istante finale? 
  - Quando N tende ad infinito cosa succede? Sia caso client-server che caso peer to peer. 
  - Qual è migliore? (Peer to peer). 
  - Perché abbiamo supposto che  tutte le velocità di upload fossero uguali?

- 🟨 tipi di approccio per strutturare il **database P2P** per distribuzione di indici e contenuti _(in particolare centralized index, query flooding e ricerca gerarchica)_

- 🟧 **BitTorrent**:
  - come funziona
  - come si fa a sapere quali peer fanno parte del torrent? 
  - Come fa un peer per entrare in un torrent e scaricare un file
  - Disegno ecosistema bit torrent, 
  - Se uno si registra con il torrent server come fa il tracker a sapere che il nuovo peer si è registrato? 
  - In generale, rapporto tra peer nuovo e tracker? 
  - Come misura lui la velocità di upload degli altri peer verso di lui? 
  - Poi fa una classifica, e una volta fatta la classifica? 
  - Cosa c’è da ricordare sulla fase di upload? 
  - Nomi del meccanismo della graduatoria e della scelta casuale? 
  - Quali sono le caratteristiche innovative di bit torrent nella condivisione di file?



### Data link layer
- 🟨 **PPP**: 
  - spiegazione dei campi address e control
  - byte stuffing
  - il formato del pacchetto
  - come si negoziano i campi inutilizzati _(**L**ink **C**ontrol **P**rotocol)_
  - A cosa servono i byte di flag _(delimitatore del frame)_
  - quale protocollo di negoziazione dei parametri del protocollo IP si usa? _(ICMP)_

- Slotted e unslotted **ALOHA**

- 🟥 **CSMA/CD**: 
	- Perché si usa questo rapporto adattivo _(si parte  piano e poi si aumenta)_

- 🟨 formato **frame ethernet**: 
  - come è formato
  - dimensione _(almeno 64byte)_

- 🟥 **CSMA/CD ethernet**: 
	- tempi sui segnali del mezzo
	- relazione tra il frame ethernet e i 512 bit time usati nel tempo di backoff
	- 51.2 microsecondi ha un qualche significato fisico? (rappresenta il bit time nel caso di connessioni a 10Mbps)


### Internetworking
- 🟧 protocollo **DHCP**: 
  - specificare i messaggi scambiati
  - schema di come  un host richiede e riceve un ip _(4 handshake)_
  - come avviene la comunicazione
  - livello in cui opera tale protocollo _(protocollo applicativo)_

- 🟧 **NAT**: 
  - a cosa serve _(assegnare un ip pubblico a più host privati)_
  - per quale scopo è stato pensato _(ridurre il numero di ip necessari)_
  - disegno di cosa succede quando si utilizza il nat  
  - limiti _(limite massimo connessioni dovuto alle porte del router, è un router nel mezzo per cui violata connessione end-to-end, la soluzione migliore è usare IPv6)_
  - come si implementa 
  - situazione particolare in cui questo meccanismo potrebbe non bastare e come si risolve _(se la richiesta parte dall'esterno potrebbe mancare l'associazione porta-ip privato, si può risolvere effettuando un port mapping manuale con iptables aggiungendo la regola)_



### Transport layer
- 🟥 **chiusura/apertura** connessione **TCP**: 
	- come funziona
	- perché il numero di sequenza iniziale è casuale _(per evitare che il client si connetta, chiuda la connessione e poi la riapra subito dopo ed allora nei buffer interni vi rimangono ancora vecchi dati)_

- 🟨 **Affidabilità** protocollo **TCP**:
  - come viene garantita _(ARQ e RTT stimato)_

- 🟨 **timeout** su reti **TCP**:
  - come si calcola
  - Perché la stima potrebbe essere troppo grande o troppo piccola 
  - perché non si tiene conto dei pacchetti perduti

- 🟨 Controllo di **flusso** nel protocollo **TCP**:
  -  a cosa serve _(evitare che il ricevitore sia inondato di dati oltre quanto il buffer può gestire)_

- 🟥 **congestione TCP**:
  - cos'è la congestione _(quando troppe sorgenti inviano troppi dati per essere gestiti dalla rete)_
  - come si gestisce con relativo diagramma di stato (fasi slow start, collision avoidance e fast recover)
  - come e dove si verifica _(router intermedi che smistano il traffico)_
  - cosa comporta per gli host _(packet loss e aumento delay)_
  - quanto vale MSS nella congestion window e come calcolarlo _(Maximum Segment Size)_

- 🟨 **Differenza** tra controllo di **flusso** e controllo di **congestione**? _(flusso è tra trasmettitore e ricevitore, congestione riguarda i router intermedi)_
- 🟨 Perché si fa un trattamento diverso tra il **timeout** e il **triplice ack**? 



### Security
- 🟨 **MAC** _(Message Authentication Code)_:
  - proprietà sue e della funzione hash utilizzata
  - controllo integrità
  - a cosa serve
  - come si implementa
  - cosa significa che un messaggio è corrotto _(che ricalcolando l'hash del messaggio il MAC  è differente)_
  - quali altri servizi _(oltre integrità)_ offre _(autenticazione se il segreto condiviso è in mano solo ai due host)_
  - cosa succede quando arriva al destinatario _(ricalcola il MAC con il segreto condiviso e verifica se combaciano)_
  - prevenire record and playback

- 🟥 **firma digitale**:
  - proprietà _(verificabilità, non alterabilità, integrità, non replicabilità)_ 
  - implementazione (con schema)
  - perchè il mac non è definibile una firma digitale

- 🟨 **metodi** per inviare una **chiave di sessione** con riservatezza 
  - con chiave pubblica _(in particolare il disegno)_
  - con chiave simmetrica e KDC _(**K**ey **D**istribution **C**enter)_

- 🟨 **PGP** _(Pretty Good Privacy)_

- 🟨 confidenzialità dei messaggi (?)

- 🟨 **SSL** _(**S**ecure **S**ocket **L**ayer)_ 
  - Qual è la caratteristica della chiave pubblica?

- 🟨 **IPsec**:
  - come si realizza
  - cosa sono le Security association


### Wireless and Mobile Network
- 🟥 problema del **nodo nascosto** e **esposto** _(con precisione, anche su cosa sono i cerchi dei disegni)_ : 
  - Da cosa deriva i nome
  -  Ci sono due modi di raffigurarlo, dirli entrambi. (Il secondo dovrebbe essere quello con un ostacolo tra A e C)
  - chi riceve i messaggi se inviati da uno specifico nodo?
  - come si risolve il problema *(virtual career sensing)*

- 🟥 protocollo **CSMA/CA**:
  - specificare i passaggi
  - calcolo del tempo di backoff
  - Far vedere i messaggi scambiati tra i vari nodi specificando i passaggi precisi e nome preciso ai messaggi (RTS, CTS)
  - specificando nel dettaglio perché **difs** e **sifs** hanno durata differente 


- 🟥 **mobile ip**: 
  - Cosa vuol dire che cambia il punto di accesso? 
  - Come possiamo permettere le continuità del servizio in caso di mobilita? (fare disegno del problema con le parti in causa)
  - Come viene gestito lo spostamento nelle due modalità di routing indiretto e diretto?
  - Quale approccio utilizza il mobile ip? _(indiretto)_


---

## Domande Pistolesi

### Progetto
La prima parte dell'esame consiste nella discussione del progetto, alcune delle domande potrebbero riguardare:
- motivare alcune scelte nel progetto
- motivare la scelta di UDP, se utilizzato
- perché sono stati utilizzati i thread nel progetto, se presenti
- perchè si è utilizzato la select, se presente
- Perché hai scelto di usare socket bloccanti con la IO-multiplexing?
- Che svantaggio avresti avuto usando quelli non bloccanti?
- Hai creato una lista di peer, dà una minore robustezza in caso di crash del server, perché? È colpa della lista?
- in caso di caduta di un device cosa succede? 
- Il fatto di mantenere sempre la connessione con il server che vantaggi e svantaggi ha?
- Come avresti fatto per implementarlo con UDP?
- nel progetto ci sono parti in cui è utile gestire la mutua esclusione?


### Parte teorica
- `ip addr show` e `ip addr add`

- quali sono i requisiti per essere connessi ad internet? 

- da dove si vede se abbiamo accesso al router di default? Qual è il suo ip? (vediamo dal file persistente in `/etc/network/interfaces` oppure col comando `ip route show`)

- da dove si vede se il dns è configurato? (guardare in `/etc/resolv.conf` per vedere se impsotato il dns server e `nslookup dominio` per testare  un dominio in particolare)

- NSS switch _(**N**ame **S**erver **S**witch)_

- come vedere se la macchina è connessa a internet e verifica configurazione

- DNS

- come vedere se una macchina ha indirizzo statico o dinamico _(più in generale anche come lo ha acquisito)_
  > Nel  file in /etc/network/interfaces si trova la spunta dhcp invece di static

- **traceroute**: 
  - come funziona
  - perché 3 pacchetti
  - perchè port unreacheable, output... 
  - quando si usa e quali sono i suoi vantaggi
  - che porte utilizza traceroute
  - fare un esempio sulla macchina virtuale del comando traceroute
  - come facciamo a capire da cosa deriva il timeout, ovvero se siamo stati noi a scartare il pacchetto oppure i destinatari _(dipende se va avanti, se procede semplicemente non era implementato per rispondere a ICMP altrimenti non abbiamo ricevuto risposta e non è raggiungibile)_
  - spiega l output cosa significa se mostra gli asterischi _(non implementato ICMP o timed out)_

- funzioni di conversione: htonl, htons, ntohl, ntohs

- problema dell **endinaness** come gestirlo _(funzioni di conversione)_

- funzioni _t, inet_pton e inet_ntop

- `socket()`, `listen()` _(cosa fa e in che momento viene chiamata nel server?)_, `accept()`, `bind()` e `connect()` come interagiscono, comportamento


- `send()` e `recv()`
  
- `select()` e le relative macro _(sapere nel dettaglio ordine e parametri)_

- differenze tra socket bloccanti e non: 
  - Dove si spostano le attese nel caso di uni e nel caso degli altri
  - Come cambiano i tempi di attesa

- `fork()`: chi duplica tutto il codice quando eseguo la fork? il sistema operativo

- **I/O multiplexing**: come funziona

- disegnare la FSM del controllo di congestione di TCP

- socket non bloccanti _(con differenze da quelli bloccanti e spiegazione diagramma temporale)_

- Differenza tra multiplexing e server concorrenti

- protocolli **Text** e **Binary** con vantaggi e svantaggi di ognuno, come inviare e ricevere in entrambi i modi

- **firewall**: cos'è, dove posso trovarlo, a cosa serve, e come si configura

- **iptables**: esempio, come aggiungere un record alla tabella

- **NAT** e **PAT**: esempio con inserimento di una regola in una chain, a cosa servono, come funzionano

-  **apache2**: 
   - struttura
   - come farlo partire
   - come si implementa
   - a cosa serve il virtual host
   - directory
   - moduli e direttive
   - file di configurazione
   - una volta che abbiamo abilitato un modulo bisogna riavviare il server?  _(Si)_
  - userdir
  - come gestisce gli utenti __(prefork, workers, event)__

- tipi certificati perchè si usano, come fare se non li uso? 
	i 2 host usano un protocollo di testo per scambiarsi i dati perchè convertendo i numeri in testo il char è sempre rappresentato con 1 byte non serve la certificazione

