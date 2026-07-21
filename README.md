# 🚀 Roberto Ingenito Portfolio

Un sito web personale e di presentazione professionale sviluppato per esporre le mie competenze, i servizi offerti e i miei progetti. Il progetto è stato pensato per essere il principale punto di ingresso per recruiter o clienti, ed è accessibile su [robertoingenito.com](https://robertoingenito.com).

## ⚙️ Architettura e Tecnologie

Questo progetto è costruito come una single-page application veloce e leggera, ed è completamente containerizzato per l'hosting.

| Tecnologia | Dettagli |
|---|---|
| **Frontend** | React 19 + TypeScript |
| **Build Tool** | Vite 8.0 |
| **Styling** | Vanilla CSS (Animazioni e Layout Custom) |
| **Deploy** | Docker (Multi-stage build: `node:24-slim` builder + `nginx:alpine` runner) |

## 🌟 Funzionalità Principali
- **Interfaccia Moderna:** Design pulito con un cursore personalizzato e sezioni chiare (Hero, Marquee, Servizi, Chi Sono, Contatti).
- **Animazioni allo Scroll:** Componenti creati ad-hoc (`Reveal.tsx`) che utilizzano custom hooks e l'Intersection Observer nativo per far comparire fluidamente gli elementi, mantenendo alte le performance senza librerie esterne.
- **Docker Ready:** Container ottimizzato grazie a Nginx, pronto per l'hosting tramite l'infrastruttura omo-lab.

## 🛠️ Prerequisiti
- [Node.js](https://nodejs.org/)
- [Docker](https://www.docker.com/) (se si desidera eseguire o testare la build containerizzata)

## 🏃‍♂️ Come Avviare il Progetto

### Sviluppo in Locale
1. Installa le dipendenze:
   ```bash
   npm install
   ```
2. Avvia il server di sviluppo tramite Vite:
   ```bash
   npm run dev
   ```
   Il progetto sarà disponibile all'indirizzo http://localhost:5173.

### Produzione con Docker
Per compilare l'immagine e testare il container con il server Nginx in locale:
```bash
docker build -t roberto-portfolio .
docker run -p 8080:80 roberto-portfolio
```
L'applicazione compilata sarà accessibile su http://localhost:8080.

## 📦 Struttura dei Componenti
La logica è interamente modulare per facilitare la manutenibilità:
- `App.tsx` - Componente root che orchestra layout globale e cursore custom.
- `/src/components` - Componenti UI isolati come `Navbar`, `Hero`, `Marquee`, `Services`, `About`, `Contact`, `Footer` e `Reveal`.
- `/src/hooks` - Custom React hooks (es. `useInView`).
- `/src/styles` - File di stile specifici dei componenti per mantenere l'ecosistema CSS pulito.

---

## 🔗 Progetti Correlati
- [Homelab Infrastructure](https://github.com/roberto-ingenito-home-lab/server-raspberry-pi) — Infrastruttura server e deployment Docker
