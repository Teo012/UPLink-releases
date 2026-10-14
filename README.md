# UPLink — aggiornamenti

Questo repository contiene **solo i pacchetti** di UPLink (l'installer per PC `.msi` e l'app per Android `.apk`) e l'elenco firmato delle versioni (`update.json` + `update.json.sig`).
Non c'è codice sorgente. È pubblico perché le app UPLink già installate possano controllare e scaricare gli aggiornamenti senza credenziali.

- Le app cercano `https://github.com/Teo012/UPLink-releases/releases/latest/download/update.json` e la sua firma.
- L'elenco è firmato (ECDSA P-256) con una chiave privata che non è qui: le app hanno dentro la chiave pubblica e **ignorano qualunque elenco non firmato bene**.
  Un file scaricato viene installato solo se dimensione e SHA-256 coincidono con quelli dell'elenco firmato.
- Le release si creano con lo script `installer/Publish-Update.ps1` del progetto UPLink: non vanno modificate a mano.

Per installare UPLink la prima volta: scarica l'ultimo `UPLink-<versione>-x64.msi` (PC) o `UPLink-Android-<versione>.apk` (Android) dalla pagina [Releases](../../releases/latest).
Windows mostrerà «Editore sconosciuto» (l'installer non è firmato con un certificato a pagamento); su Android serve consentire l'installazione da «app sconosciute».
