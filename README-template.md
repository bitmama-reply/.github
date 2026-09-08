<!--
  Template README per i repository bitmama-reply.
  Copialo in un nuovo repo, compila ogni sezione, cancella questo commento.
  Un README con sezioni vuote è peggio di uno corto: togli quelle che non servono.
-->

# Nome progetto

Una riga: cosa fa e per chi. Stessa frase della *Description* del repository.

**Cliente:** Nome cliente · **Referente tecnico:** @nome.cognome · **Stato:** attivo

## Ambienti

| Ambiente | URL | Branch | Note |
| --- | --- | --- | --- |
| Produzione | https:// | `main` | |
| Staging | https:// | `develop` | |
| Locale | http://localhost:3000 | — | |

## Stack

Framework, CMS, servizi esterni, versioni vincolanti. Solo ciò che sorprenderebbe chi apre il repo per la prima volta.

- Runtime: Node 20
- CMS:
- Hosting:
- Servizi terzi:

## Avvio locale

```bash
git clone git@github.com:bitmama-reply/<repo>.git
cd <repo>
cp .env.example .env   # le credenziali sono su <dove>
npm ci
npm run dev
```

Prerequisiti non ovvi (versione di PHP, un container, un accesso VPN, un file di dump) vanno elencati qui, non dati per scontati.

## Rilascio

Come va in produzione: pipeline, comando, approvazioni necessarie, chi può farlo.

```bash
# esempio
git checkout main && git pull
npm run deploy:prod
```

Rollback: come si torna indietro e in quanto tempo.

## Struttura

Solo le directory che non si spiegano da sole.

```
src/
  components/
  content/     # ← contenuti statici, non toccare a mano: generati da <x>
scripts/
```

## Cose da sapere

Le trappole. Il workaround che sembra un bug ma è voluto. Il servizio che va giù il primo del mese. La parte di codice che nessuno ha più toccato dal 2023.

## Documentazione collegata

- Decisioni tecniche: [`docs/adr/`](docs/adr/)
- Board / ticket:
- Design:
- Documentazione cliente:
