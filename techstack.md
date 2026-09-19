# Teknologistakk for Achtung, die Kurve! (Kurvefeber)

Applikasjonen er bygget som en ren, moderne **Single-Page Application (SPA)** i én enkelt selvstendig HTML-fil, spesialdesignet for å kunne kjøre sømløst direkte fra **GitHub Pages** uten behov for ekstern server, backend-database eller komplisert byggesett (build tools).

## 1. Frontend & Grensesnitt
*   **HTML5 / Canvas API:** Hovedspillmotoren er bygget på HTML5 `<canvas>` for rask 2D-rendering av ormer, spor, power-ups og partikkeleffekter.
*   **Tailwind CSS:** Brukes til alt design, grid-systemer, knapper, modaler og responsiv layout via CDN.
*   **FontAwesome (v6.4.0):** Ikoner for menyer, kontroller, lyd og fullskjermknapper.
*   **Google Fonts:** Bruker *Rajdhani* for moderne, futuristisk spilltekst og *Press Start 2P* for retro arcade-elementer.

## 2. Spillmotor & Fysikk
*   **Egendefinert 60 FPS Spillmotor:** Skrevet i ren JavaScript med **Delta-tid (Delta-Time / dt)** for jevn kjøring uavhengig av skjermens oppdateringsfrekvens (60Hz, 120Hz, 144Hz osv.).
*   **CPU-basert Rutenett (Grid):** Bruker et effektivt logisk `Uint8Array`-rutenett i bakgrunnen for pikselpresis kollisonsdeteksjon uten treg GPU-lesing (`getImageData`), kombinert med en hale-buffer for å forhindre falske selv-kollisjoner.

## 3. Nettverk & Multiplayer (P2P WebRTC)
*   **PeerJS (v1.5.4):** Muliggjør null-konfigurasjons **WebRTC peer-to-peer-kommunikasjon**. Vertsskjermen (f.eks. PC eller TV) fungerer som server, og mobiler kobler seg direkte til via datakanaler.
*   **Dynamisk QR-kodeskaper:** Bruker `qrserver.com`-API-et til å generere en skannbar QR-kode med en unik 4-sifret romlenke for lynrask tilkobling fra mobilkamera.

## 4. Lyd & Streaming
*   **Web Audio API:** Innebygd syntetisk lydprosessor som genererer retro lydeffekter (kollisjoner, power-ups, nedtelling og seiersfanfare) i sanntid uten eksterne lydfiler (`.mp3` / `.wav`).
*   **Google Cast Sender Framework:** Integrert for å støtte casting av spillskjermen direkte til Chromecast og Smart-TV-er fra Google Chrome.