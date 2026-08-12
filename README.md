# Gamers Club — gamersclub.it

Landing page statica per l'associazione di videogiocatori di San Donà di Piave (fase esplorativa: raccolta interessati).

## Struttura

- `index.html` — l'intera pagina (unica pagina, HTML puro)
- `src/input.css` — sorgente Tailwind con i token di design (colori, font)
- `assets/style.css` — CSS compilato (committato: il deploy non richiede build)

## Sviluppo

```sh
npm install
npm run watch   # ricompila il CSS a ogni modifica
npm run dev     # serve il sito su http://localhost:3000
```

Dopo aver modificato classi in `index.html` o token in `src/input.css`, ricompila con `npm run build` (o lascia attivo `npm run watch`).

## Cose da fare prima del lancio

Cerca `TODO` in `index.html`:

1. **Email** — sostituisci `info@gamersclub.it` con l'indirizzo reale (compare in 2 punti) e configura la casella o un redirect sul dominio.
2. **Discord/Telegram** — quando crei il gruppo, metti il link d'invito al posto di `#` nel bottone "Gruppo Discord · in arrivo" e rimuovi le classi `pointer-events-none`, `border-white/25`, `text-white/50` (usa ad es. `border-white/60 text-white hover:bg-white/10`).
3. **Instagram** — aggiorna la riga "Presto anche su Instagram" con il link al profilo.

## Deploy su Vercel

```sh
npm i -g vercel
vercel          # primo deploy (rispondi alle domande, framework: Other)
vercel --prod   # deploy in produzione
```

Poi collega il dominio: su vercel.com → progetto → Settings → Domains → aggiungi `gamersclub.it` e segui le istruzioni per puntare i DNS del registrar (record A `76.76.21.21` oppure nameserver Vercel).

In alternativa: pusha il repo su GitHub e importalo da vercel.com/new — ogni push farà un deploy automatico. Nessuna configurazione di build necessaria: il CSS compilato è già nel repo.
