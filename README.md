# CardScan 📇

Webapp mobile per scansionare biglietti da visita **fronte + retro** con correzione prospettica automatica.

## Funzionalità

- 📷 Apertura fotocamera posteriore del cellulare
- 🔍 Rilevamento automatico bordi del biglietto in tempo reale (OpenCV.js)
- 📐 Correzione prospettica automatica (warpPerspective)
- 🔄 Scansione fronte + retro
- 🖼️ Composizione finale affiancata (fronte a sx, retro a dx)
- 💾 Salvataggio PNG in download

---

## Come pubblicare su GitHub Pages

### 1. Crea un repository

- Vai su [github.com](https://github.com) → **New repository**
- Nome suggerito: `cardscan`
- Visibilità: **Public** (necessario per GitHub Pages gratuito)
- Clicca **Create repository**

### 2. Carica i file

- Clicca **Add file → Upload files**
- Trascina il file `index.html`
- Clicca **Commit changes**

### 3. Attiva GitHub Pages

- Vai su **Settings** → sezione **Pages** (nel menu laterale)
- In **Source** seleziona: `Deploy from a branch`
- Branch: `main` → cartella: `/ (root)`
- Clicca **Save**

### 4. Accedi alla webapp

Dopo 1-2 minuti il sito sarà disponibile all'indirizzo:

```
https://TUONOME.github.io/cardscan/
```

> ⚠️ La webapp funziona solo via **HTTPS** (GitHub Pages lo fornisce automaticamente).  
> Su HTTP la fotocamera non parte per motivi di sicurezza del browser.

---

## Come si usa

1. Apri il link dal **browser del cellulare** (Safari su iPhone, Chrome su Android)
2. Consenti l'accesso alla fotocamera
3. Punta il biglietto: appare il rettangolo di rilevamento
4. Quando il contorno è **verde e stabile** → premi **SCATTA FRONTE**
5. Gira il biglietto → ripeti per il **RETRO**
6. Vedi l'anteprima affiancata → premi **SALVA IN PNG**

> Se il rilevamento automatico non funziona bene (sfondo difficile),  
> usa il pulsante **SCATTA SENZA RILEVAMENTO** per catturare comunque.

---

## Tecnologie usate

| Libreria | Versione | Uso |
|----------|----------|-----|
| [OpenCV.js](https://docs.opencv.org/4.8.0/d5/d10/tutorial_js_root.html) | 4.8.0 | Edge detection + perspective warp |
| HTML5 Canvas API | — | Rendering overlay e composizione |
| MediaDevices API | — | Accesso fotocamera |

---

## Note

- Il file è **100% statico** (solo `index.html`), nessun server necessario
- I dati non vengono mai inviati da nessuna parte — tutto elaborato localmente nel browser
- OpenCV.js (~8MB) viene caricato una sola volta e messo in cache dal browser
