# 🚀 B2B SaaS Architecture & Middleware Portfolio
**Antoniangelo Flore** — *Fractional CTO & B2B Software Architect*

> 🔒 **Nota sulla Proprietà Intellettuale:**  
> Il codice sorgente dei moduli SaaS, dei Gateway e degli ETL elencati di seguito è **proprietario e protetto in repository privati**. Questo repository pubblico funge da documentazione architetturale per illustrare logiche, stack e ROI delle infrastrutture che progetto per le Agenzie Web e PMI.

---

## ⚙️ Il Motore: B2B Gateway Hub (Choke Point Asincrono)
Un middleware centralizzato in **Node.js/Express** progettato per assorbire il carico ETL (Extract, Transform, Load) delle agenzie web. Agisce da scudo tra le API dei clienti e i servizi esterni.

*   **Il Problema:** I server delle agenzie crashano sotto i picchi di chiamate API o per guasti di servizi terzi (Data Pollution).
*   **La Soluzione:** Architettura Zero-Trust con Rate Limiting, autenticazione unificata e instradamento intelligente.
*   **Tolleranza ai Guasti (Filtro Amazon):** Implementazione nativa di **Dead Letter Queue (DLQ)** e Idempotenza. Nessun dato logistico o lead viene mai perso se un server esterno va offline. I payload falliti vengono salvati su DB locale e riprocessati in asincrono.

---

## 📦 Smart Data Importer (ETL Listini)
Applicazione standalone (PHP 8/MySQL) integrabile in ecosistemi e-commerce per automatizzare il caricamento massivo dei cataloghi fornitori.

*   **Leva B2B:** Sostituisce 15+ ore mensili di data-entry manuale.
*   **Logica Operativa:** Ingerisce file CSV/XML, rileva anomalie di tracciamento, esegue il merge dei duplicati e inietta i dati sanitizzati nei gestionali (es. WooCommerce) tramite Webhook, senza bloccare la UI dell'operatore.

---

## 🤖 Automazione e Data Scraping (Chrome Extensions MV3)
Sviluppo di estensioni Chrome native (Manifest V3) per l'ingestione dati e l'automazione stealth.

*   **AI CV Generator:** Cattura dati dal DOM di portali lavorativi, li processa via API Multi-Provider (OpenRouter, Groq) e genera output strutturato.
*   **B2B Lead Scraper:** Modulo in grado di eludere i filtri agganciandosi direttamente al browser dell'operatore, popolando database MySQL per l'invio drip di cold email tramite crons su VPS Linux.

---
📫 **Contatti:** Per licenze White-Label o consulenza infrastrutturale, visita [antoniangeloflore.com](https://antoniangeloflore.com).
