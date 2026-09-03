# La mia libreria
Applicazione web single-page leggera e autonoma per la gestione della libreria personale. Il cuore dell'app è un singolo file HTML contenente CSS e JavaScript: non richiede installazione, server backend o processi di compilazione, e può ancora essere scaricato e aperto da solo in qualsiasi browser.

## Scopo del progetto
L'obiettivo è fornire uno strumento immediato e portabile per tracciare i libri letti e la lista dei desideri. L'interfaccia è progettata per funzionare fluidamente sia su desktop che su dispositivi mobili, offrendo un'alternativa rapida alle app native senza dipendenze complesse.

## Funzionalità principali
- Architettura Single-File: L'intera applicazione risiede in `index.html`. Basta scaricare quel file e aprirlo in qualsiasi browser per usarla offline, senza gli altri file del repository.
- Integrazione Google Books e Open Library: Ricerca in tempo reale tramite API pubbliche per recuperare automaticamente metadati e copertine, con fallback tra le due fonti.
- Aggiunta manuale: se un libro non si trova online, può essere inserito a mano con tutti i suoi dati, dalla vista Cerca o direttamente da Desideri/Letti.
- Valutazioni e note personali: ogni libro può avere una valutazione a stelle (1-5) e note libere, visibili in anteprima nelle card della lista.
- Gestione Liste: Separazione tra libri "Letti" e "Desideri", con filtraggio, ordinamento per data/titolo/autore (crescente o decrescente) e visualizzazione a griglia o lista.
- Statistiche di lettura: vista dedicata con totali, pagine lette, andamento degli ultimi 6 mesi, autori più letti e ripartizione cartaceo/ebook.
- Backup e Ripristino: Sistema integrato di Export/Import in formato CSV standard per salvare i dati o trasferirli tra dispositivi, con rilevamento dei duplicati in fase di import.
- UI Responsive e accessibile: Layout adattivo (barra di navigazione inferiore su mobile, sidebar su desktop), navigabile da tastiera, con focus visibile, chiusura del modal con Esc e focus trap.
- Persistenza Locale: Utilizza il LocalStorage del browser per salvare i dati istantaneamente senza necessità di login o account.
- PWA opzionale: se pubblicata su un server web (es. GitHub Pages), l'app può essere installata su mobile/desktop e continua a funzionare offline grazie a `manifest.json` e `service-worker.js`. Questi file sono complementari: se mancano (es. si scarica solo `index.html`), l'app funziona comunque, semplicemente senza installabilità.

## Limiti tecnici
- Archiviazione Locale: I dati risiedono esclusivamente nella cache/storage del browser in uso. Se i dati del sito vengono cancellati, si perdono (a meno che non sia stato effettuato un backup CSV).
- Nessuna Sincronizzazione Cloud: Non essendoci un database centrale, i dati non si sincronizzano automaticamente tra diversi dispositivi o browser. Il trasferimento deve avvenire manualmente tramite file CSV.
- Dipendenza API: La ricerca di nuovi libri richiede una connessione internet attiva per interrogare Google Books e Open Library; l'aggiunta manuale resta disponibile anche offline (dati già in cache) o quando le API non rispondono.
