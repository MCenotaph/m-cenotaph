# M. CENOTAPH — AUTHORIZED ACCESS TERMINAL

Sito-archivio per il progetto musicale **M. Cenotaph**.  
Single file HTML — nessuna dipendenza, nessun build step, nessun framework.

---

## Struttura del progetto

```
/
├── index.html                        # Tutto il sito (HTML + CSS + JS inline)
├── README.md                         # Questo file
│
├── MCenotaph_VACUUM_SEALED.mp3       # FILE_001 — sempre disponibile
├── MCenotaph_SWEET_DESCENT.mp3       # EVIDENCE_A — sempre disponibile
│
├── MCenotaph_SILK_GARROTTE.mp3       # FILE_002 — codice: ASPHYXIA
├── MCenotaph_GHOST_PROTOCOL.mp3      # FILE_003 — codice: PHANTOM
├── MCenotaph_MARBLE_FACE.mp3         # FILE_004 — codice: MARBLE
├── MCenotaph_GOLDEN_DECAY.mp3        # FILE_005 — codice: DECAY
├── MCenotaph_ARCHITECT_OF_VOID.mp3   # ARCHIVE_LOG — codice: BLUEPRINT
│
├── MCenotaph_REQUIEM.mp3             # FILE_009 — codice: 666
├── MCenotaph_ABSOLUTE_ZERO.mp3       # FILE_010 — codice: 999
│
├── MCenotaph_EMPLOYEE_OF_THE_MONTH.mp3  # FILE_006 — Gold: COMMENDED
├── MCenotaph_THE_CUSTOMER_IS_KING.mp3   # FILE_007 — Gold: SOVEREIGN
├── MCenotaph_PRESSURE_COOKER.mp3        # FILE_008 — Gold: THRESHOLD
│
├── MCenotaph_CENOTAPH_INTRO.mp3      # Intro neuro-link screen
├── MCenotaph_FRAGMENT_DREAM.mp3      # Minigame Memory Protocol
├── MCenotaph_COLD_OPTICS.mp3         # Minigame Signal Scan
├── MCenotaph_GLASS_TEARS.mp3         # Minigame Glass Tears
├── MCenotaph_THE_LEGACY.mp3          # Gold Mode bonus
│
└── MCenotaph_THE_OPEN_SHELL.mp3      # BONUS_001 — morse SOS / codice: SOS
```

---

## Flusso utente

```
BOOT SCREEN
  └─ animazione terminale → tasto ENTER
      └─ NEURO-LINK SCREEN
            ├─ ascoltare l'intro (69 secondi) → accesso
            └─ oppure inserire un codice valido nel bypass
                └─ MAIN ARCHIVE
```

---

## Sistema di sblocco

### Vault (input testuale)
Il Vault è nella sezione principale. Si inserisce un codice e si preme ENTER.

| Codice | File sbloccato |
|---|---|
| `ASPHYXIA` | FILE_002 — Silk Garrotte |
| `PHANTOM` | FILE_003 — Ghost Protocol |
| `MARBLE` | FILE_004 — Marble Face |
| `DECAY` | FILE_005 — Golden Decay |
| `BLUEPRINT` | ARCHIVE_LOG — Architect of Void |
| `666` | FILE_009 — Requiem |
| `999` | FILE_010 — Absolute Zero |
| `SOS` | BONUS_001 — The Open Shell |

### Gold Mode (sblocca files esclusivi)
Gold Mode si attiva automaticamente quando tutti i 10 file sono recuperati, oppure inserendo `GOLDMODE` nel vault.  
In Gold Mode si sbloccano tre file aggiuntivi:

| Codice | File sbloccato |
|---|---|
| `COMMENDED` | FILE_006 — Employee of the Month |
| `SOVEREIGN` | FILE_007 — The Customer Is King |
| `THRESHOLD` | FILE_008 — Pressure Cooker |

### Codici speciali

| Codice | Effetto |
|---|---|
| `ALGOR_MORTIS` | God Mode — sblocca tutto |
| `GOLDMODE` | Attiva Gold Mode manualmente |
| `NECROSIS` | Toggle glitch visivo (inserire di nuovo per rimuoverlo) |
| `ORCHESTRA` | Sblocca e inietta player per 666 e 999 nel vault |
| `EPIGRAFE` | Salta l'intro neuro-link |

### Minigame
Tre sezioni con minigame che sbloccano file extra una volta completati:

| Sezione | Minigame | File |
|---|---|---|
| SECTION_03 | Memory Protocol (sequenza 4×4) | Fragment Dream |
| SECTION_04 | Signal Scan (tuner radio) | Cold Optics |
| SECTION_05 | Glass Tears (intercetta segnali) | Glass Tears |

### Morse — BONUS_001 (The Open Shell)
Due dot morse sono presenti nell'interfaccia:

**Dot sinistro** — solo broadcast, `pointer-events: none`. Trasmette in loop il messaggio `ALL PERISH DOES HASTE ALTER THE END`.

**Dot destro** — interattivo. Cliccarci sopra per inserire morse manualmente:

- Click breve = `.` (punto)
- Click lungo (>380ms) = `—` (tratto)
- Pausa ~900ms = fine lettera (flash bianco di conferma)
- Pausa ~2.8s = reset completo

Digitare `SOS` (`... --- ...`) sblocca **The Open Shell**. In alternativa, inserire `SOS` direttamente nel vault.

---

## Easter eggs & secrets

- **Ghost Typer** — dopo 3 minuti di inattività appare un cursore fantasma che tenta codici errati nel vault. Dopo 6 minuti tenta codici parziali e cancella tutto senza inviare.
- **Starfield** — stellato visibile solo tra le 23:00 e le 05:00 (ora locale), oppure sempre attivo in Gold Mode con meteore dorate.
- **Cursor trail** — particelle seguite dal mouse.
- **System Integrity Bar** — barra in cima, cresce ad ogni file sbloccato. A 100% attiva Gold Mode.
- **Gold Mode** — palette oro, meteore, fuochi d'artificio, Legacy bonus track.

---

## Audio player — note tecniche

Tutti i player usano un sistema unificato (`wireAllPlayers` + `wirePlayer` per i locked).  
La barra di avanzamento supporta **drag** (mousedown → mousemove → mouseup) oltre al click.  
Un singolo `stopOthers()` garantisce che una sola traccia suoni alla volta.  
Web Audio API attiva il visualizzatore a barre durante la riproduzione.

---

## Deployment

Nessun server necessario per la struttura HTML/CSS/JS.  
I file `.mp3` devono essere nella stessa directory di `index.html`.  
Per hosting su server con CORS: assicurarsi che i file audio vengano serviti con `Content-Type: audio/mpeg`.

---

## Changelog

### Ultima sessione
- Aggiunto **BONUS_001 — The Open Shell** (sblocco via morse dot destra o codice `SOS` nel vault)
- Morse sinistra: ripristinato passivo, solo broadcast, `pointer-events: none`
- Morse destra: nuovo elemento interattivo `#morse-dot-sos`, area click ampliata
- `SOS` aggiunto come codice vault valido con handler dedicato
- Progress bar: sistema drag completo su tutti i player (mousedown → mousemove → mouseup)
- Descrizioni card: accorciate e riscritte, meno ridondanza
- Boot log: corretti i nomi FILE_009 e FILE_010
