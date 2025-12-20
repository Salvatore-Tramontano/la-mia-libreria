# La mia libreria
Applicazione web single-page leggera e autonoma per la gestione della libreria personale. Sviluppata interamente in un singolo file HTML contenente CSS e JavaScript, non richiede installazione, server backend o processi di compilazione.

## Scopo del progetto
L'obiettivo è fornire uno strumento immediato e portabile per tracciare i libri letti e la lista dei desideri. L'interfaccia è progettata per funzionare fluidamente sia su desktop che su dispositivi mobili, offrendo un'alternativa rapida alle app native senza dipendenze complesse.

## Funzionalità principali
- Architettura Single-File: L'intera applicazione risiede in un unico file .html. Basta scaricarlo e aprirlo in qualsiasi browser.
- Integrazione Google Books: Ricerca in tempo reale tramite API pubbliche per recuperare automaticamente metadati e copertine.
- Gestione Liste: Separazione tra libri "Letti" e "Desideri", con opzioni di filtraggio, ordinamento per data e visualizzazione a griglia o lista.
- Backup e Ripristino: Sistema integrato di Export/Import in formato CSV standard per salvare i dati o trasferirli tra dispositivi.
- UI Responsive: Layout adattivo che presenta una barra di navigazione inferiore su mobile e una sidebar laterale su desktop.
- Persistenza Locale: Utilizza il LocalStorage del browser per salvare i dati istantaneamente senza necessità di login o account.

## Limiti tecnici
- Archiviazione Locale: I dati risiedono esclusivamente nella cache del browser. Se la cache viene svuotata, i dati vengono persi (a meno che non sia stato effettuato un backup CSV).
- Nessuna Sincronizzazione Cloud: Non essendoci un database centrale, i dati non si sincronizzano automaticamente tra diversi dispositivi. Il trasferimento deve avvenire manualmente tramite file CSV.
- Dipendenza API: La ricerca di nuovi libri richiede una connessione internet attiva per interrogare i server di Google Books.
