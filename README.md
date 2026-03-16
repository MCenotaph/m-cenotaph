# M. CENOTAPH — AUTHORIZED ACCESS TERMINAL

Sito-archivio per il progetto musicale **M. Cenotaph**.  
Single file HTML — nessuna dipendenza, nessun build step, nessun framework.

---

## Struttura del progetto

```
/
├── index.html                         # Tutto il sito (HTML + CSS + JS inline)
├── README.md                          # Questo file
│
├── THEMONOLITH.mp3                    # ARCHIVE_000 — intro neuro-link screen
│
├── VACUUMSEALED.mp3                   # FILE_001 — disponibile all'avvio
├── SWEETDESCENT.mp3                   # EVIDENCE_A — sblocco sequenziale (001→)
├── SILKGARROTTE.mp3                   # FILE_002 — sblocco sequenziale (002→)
├── GHOSTPROTOCOL.mp3                  # FILE_003 — sblocco sequenziale (003→)
├── MARBLEFACE.mp3                     # FILE_004 — sblocco sequenziale (004→)
├── GOLDENDECAY.mp3                    # FILE_005 — sblocco sequenziale (005→)
│
├── ARCHITECTOFVOID.mp3                # ARCHIVE_LOG — codice vault: BLUEPRINT
├── ABSOLUTEZERO.mp3                   # FILE_666 — codice vault: 666
├── REQUIEM.mp3                        # FILE_999 — codice vault: 999
│
├── EMPLOYEEOFTHEMONTH.mp3             # FILE_006 — Gold Mode: COMMENDED
├── THECUSTOMERISKING.mp3              # FILE_007 — Gold Mode: SOVEREIGN
├── PRESSURECOOKER.mp3                 # FILE_008 — Gold Mode: THRESHOLD
│
├── FRAGMENTEDDREAM.mp3                # SECTION_03 — minigame Memory Protocol
├── COLDOPTICS.mp3                     # SECTION_04 — minigame Signal Scan
├── GLASSTEARS.mp3                     # SECTION_05 — minigame Glass Tears
│
├── THEOPENSHELL.mp3                   # BONUS_001 — morse SOS / codice: SOS
├── MOSCOWGHOSTLULLABY.mp3             # BONUS_002 — codice vault: PRIOR
├── GOLDPLATEDGRAVITY.mp3              # BONUS_003 — codice vault: GRAVITY
│
├── THELEGACY.mp3                      # FILE_RESTORED — Gold Mode bonus (auto)
└── THEESTATEOFM.mp3                   # FILE_TERMINAL — Gold Mode bonus (auto)
```

> **Nota:** tutti i file `.mp3` devono essere nella stessa directory di `index.html`.  
> 22 file totali (inclusi neuro-link intro e bonus chain).  
> Nessun prefisso, nessuno spazio, solo uppercase.

---

## Flusso utente

```
BOOT SCREEN
  └─ animazione terminale (log archivio) → tasto ENTER
      └─ NEURO-LINK SCREEN (ARCHIVE_000 — The Monolith)
            ├─ ascoltare l'intro (69 secondi) → accesso
            └─ oppure inserire un codice valido nel bypass
                └─ MAIN ARCHIVE
```

---

## Sistema di sblocco

### Catena Sequenziale (ascolto)
Le prime sei tracce si sbloccano in sequenza: ascoltare oltre i **10 secondi** attiva il file successivo. Non serve nessun codice.

| Condizione | File sbloccato |
|---|---|
| Avvio | FILE_001 — Vacuum Sealed |
| Ascolta 001 (>10s) | EVIDENCE_A — Sweet Descent |
| Ascolta 002 (>10s) | FILE_002 — Silk Garrotte |
| Ascolta 003 (>10s) | FILE_003 — Ghost Protocol |
| Ascolta 004 (>10s) | FILE_004 — Marble Face |
| Ascolta 005 (>10s) | FILE_005 — Golden Decay |

### Vault (codice testuale)
Il Vault è nella sezione principale. Si inserisce un codice e si preme ENTER.

| Codice | File sbloccato | Signature line |
|---|---|---|
| `ASPHYXIA` | FILE_002 — Silk Garrotte | *The finest thing they gave me was the thing that tied the knot.* |
| `PHANTOM` | FILE_003 — Ghost Protocol | *The system does not require the occupant to be present. Only operational.* |
| `MARBLE` | FILE_004 — Marble Face | *Stability and vitality are separate indices.* |
| `DECAY` | FILE_005 — Golden Decay | *The structure sings as it disintegrates.* |
| `BLUEPRINT` | ARCHIVE_LOG — Architect of Void | *The workmanship is noted.* |
| `666` | FILE_666 — Absolute Zero | *The void was always the content.* |
| `999` | FILE_999 — Requiem | *The cello stops mid-phrase. The silence is the final note.* |
| `SOS` | BONUS_001 — The Open Shell | *Not armour. Not monument.* |
| `PRIOR` | BONUS_002 — Moscow Ghost Lullaby | *Classification: prior.* |
| `GRAVITY` | BONUS_003 — Gold Plated Gravity | *No cage required. The gold is sufficient.* |

> I codici vault possono essere usati anche come bypass nel Neuro-Link screen.

### Bonus Chain (ascolto)
Una volta ascoltati i bonus B001, B002 e B003 (ognuno oltre i 10 secondi), si sblocca automaticamente:

| Condizione | File sbloccato |
|---|---|
| B001 + B002 + B003 heard | BONUS_004 — The Only Hand |

### Gold Mode (file esclusivi)
Gold Mode si attiva automaticamente quando tutti i 20 file sono recuperati, oppure con il codice `GOLDMODE`.  
In Gold Mode vengono sbloccati tre file aggiuntivi via codice e due vengono iniettati automaticamente:

| Codice | File sbloccato |
|---|---|
| `COMMENDED` | FILE_006 — Employee of the Month |
| `SOVEREIGN` | FILE_007 — The Customer Is King |
| `THRESHOLD` | FILE_008 — Pressure Cooker |
| *(auto)* | FILE_RESTORED — The Legacy |
| *(auto)* | FILE_TERMINAL — The Estate of M. |

### Codici speciali

| Codice | Effetto |
|---|---|
| `ALGOR_MORTIS` | God Mode — sblocca tutto |
| `GOLDMODE` | Attiva Gold Mode manualmente |
| `NECROSIS` | Toggle glitch visivo |
| `ORCHESTRA` | Sblocca player ambient per FILE_666 e FILE_999 |
| `EPIGRAFE` | Salta il Neuro-Link screen |

### Minigame
Tre sezioni con minigame che sbloccano file extra una volta completati:

| Sezione | Minigame | File |
|---|---|---|
| SECTION_03 | Memory Protocol (griglia 4×4) | Fragmented Dream |
| SECTION_04 | Signal Scan (tuner radio) | Cold Optics |
| SECTION_05 | Glass Tears (intercetta segnali cadenti) | Glass Tears |

### Morse — BONUS_001 (The Open Shell)
Due dot morse nell'interfaccia:

**Dot sinistro** — broadcast passivo, `pointer-events: none`. Trasmette in loop `ALL PERISH DOES HASTE ALTER THE END`.

**Dot destro** — interattivo. Click per inserire morse manualmente:
- Click breve = `.` (punto)
- Click lungo (>380ms) = `—` (tratto)
- Pausa ~900ms = fine lettera
- Pausa ~2.8s = reset

Digitare `SOS` (`... --- ...`) sblocca **The Open Shell**. In alternativa: codice `SOS` nel vault.

---

## Aure sonore — Genre Map

Il progetto segue il **Fragile Mind Protocol**: una voce sola che oscilla tra fredda analisi e disperazione melodica.

| Area | Tracce | Genere |
|---|---|---|
| IL CROLLO / ABUSO | 001, 003 | Dark Neurofunk / Industrial |
| LA MALINCONIA / LUTTO | 002, 009, B004 | Cinematic Liquid DnB / Neo-Classical / Desolate Ambient |
| LA FOLLIA / DISSOCIAZIONE | 004, 007 | IDM / Glitch Electronica |
| IL LAVORO / L'AUTOMA | 010, 011, 012 | Minimal Glitch Techno / Dark Jazz |

---

## Easter eggs & secrets

- **Ghost Typer** — dopo 3 min di inattività appare un cursore fantasma che tenta codici errati nel vault. Dopo 6 min tenta parziali e cancella senza inviare.
- **Starfield** — visibile solo tra le 23:00 e le 05:00 (ora locale), oppure sempre attivo in Gold Mode con meteore dorate.
- **Cursor trail** — particelle che seguono il mouse.
- **System Integrity Bar** — barra in cima, cresce ad ogni file sbloccato (20 slot totali). A 100% attiva Gold Mode.
- **Gold Mode** — palette oro, meteore, fuochi d'artificio, The Legacy + The Estate of M. iniettati.
- **Archivio console** — aprire DevTools → Console per hint nascosti.

---

## Audio player — note tecniche

Tutti i player usano un sistema unificato (`wireAllPlayers` + `wireSeqPlayer` per la catena sequenziale + `wirePlayer` per i vault unlocks).  
La barra di avanzamento supporta **drag** completo (mousedown → mousemove → mouseup).  
`stopOthers()` garantisce una sola traccia attiva alla volta.  
Web Audio API attiva il visualizzatore a barre durante la riproduzione.

---

## Deployment

Nessun server necessario per la struttura HTML/CSS/JS.  
I file `.mp3` devono essere nella **stessa directory** di `index.html`.  
Per hosting con CORS: servire i file audio con `Content-Type: audio/mpeg`.

---

## Changelog

### Sessione corrente — Genre Diversification + Sequential Chain
- **ARCHIVE_000 — The Monolith**: intro rinominato, nuovo concept (Dio Robotico → whisper → drop)
- **Catena sequenziale attiva**: 001→002→003→004→005→006, sblocco a >10s di ascolto
- **EVIDENCE_A bloccata** all'avvio: sblocca dopo 001
- **BONUS_003 — Gold Plated Gravity** aggiunto (`GRAVITY`) con card HTML e player
- **THE_ESTATE_OF_M** iniettato in Gold Mode insieme a THE_LEGACY
- **FILE_666 = Absolute Zero**, **FILE_999 = Requiem** (swap corretto)
- **Codice LOVE → PRIOR** (signature: *Classification: prior.*)
- **Tutti i nomi mp3** ora in formato `NOMEBRANO.mp3` senza spazi né prefissi
- Descrizioni carte aggiornate con generi e signature lines del docx
- Ticker, epigrafe quotes, boot log, hero subtitle aggiornati al nuovo concept
- BPM panel: `182` → `VARIABLE`
- Vault doc: "Investment Memorandum" → "Archive Manifest"
- Contatori: `02 / 12` → `01 / 20`, integrity bar 10→20 slot

### Sessione corrente — BONUS_004
- **BONUS_004 — The Only Hand** aggiunto: Sparse Cinematic Ambient / Desolate Trip-Hop
- Unlocks dopo che B001+B002+B003 sono stati ascoltati (>10s ciascuno) — bonus chain automatica
- Tono: la tristezza resta — la consapevolezza fa male ma non salva
- Signature: *"The only hand coming through that door is the one at the end of your arm."*
- Counters aggiornati: 21 files totali

### Sessione precedente — Genre Diversification + Sequential Chain
- Aggiunto **BONUS_001 — The Open Shell** (morse SOS o codice `SOS`)
- Morse destra: interattiva; sinistra: broadcast passivo
- Progress bar: drag completo su tutti i player
- Boot log: manifest archivio con tutti i file
