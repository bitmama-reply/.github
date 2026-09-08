# Contribuire ai repository bitmama-reply

Regole valide per tutti i repository dell'organizzazione che non definiscono le proprie.

## Metadati obbligatori del repository

Ogni repository deve avere, entro il primo giorno di vita:

| Cosa | Dove | Esempio |
| --- | --- | --- |
| Descrizione in una riga | campo *Description* | `Portale clienti Hera — Next.js + Liferay headless` |
| Cliente | topic `client-<slug>` | `client-hera` |
| Stack | topic `stack-<slug>` (uno o più) | `stack-nextjs` `stack-wordpress` |
| Stato | topic `status-<slug>` | `status-active`, `status-maintenance`, `status-dormant` |
| Referente | `CODEOWNERS` | `* @nome.cognome` |

Questi metadati alimentano l'[indice dei progetti](https://github.com/bitmama-reply) sulla home dell'organizzazione. Un repository senza `client-*` compare come "Senza cliente assegnato".

Se `status-*` non è presente, lo stato viene dedotto dall'ultimo push: attivo entro 90 giorni, in manutenzione entro un anno, dormiente oltre. Il topic esplicito serve quando la deduzione sbaglia — per esempio un progetto in manutenzione contrattuale che non riceve commit da mesi.

## README

Usa `README-template.md` di questo repository come base. Le cinque sezioni non negoziabili sono: cosa fa, ambienti, come si avvia in locale, come si rilascia, chi lo segue.

## Branch e commit

- `main` è protetto: si entra solo via pull request.
- Branch di lavoro: `feat/<breve-descrizione>`, `fix/<breve-descrizione>`, `chore/<breve-descrizione>`.
- Messaggi di commit in [Conventional Commits](https://www.conventionalcommits.org/): `feat:`, `fix:`, `chore:`, `docs:`, `refactor:`.

## Decisioni tecniche

Le scelte che qualcuno rimetterà in discussione fra un anno vanno in `docs/adr/`, un file per decisione, formato `NNNN-titolo-in-kebab-case.md`:

```markdown
# 0003 — Passaggio a Liferay headless

**Data:** 2026-03-12 · **Stato:** accettata · **Decisori:** @nome, @nome

## Contesto
Cosa rendeva necessaria una decisione.

## Decisione
Cosa abbiamo scelto.

## Conseguenze
Cosa diventa più facile, cosa più difficile, cosa va rivisto e quando.
```

Un ADR non si modifica dopo l'accettazione: se la decisione cambia, se ne scrive uno nuovo che supera il precedente.

## Fine progetto

Quando un progetto chiude:

1. Aggiorna il README con lo stato finale e l'URL di produzione se resta online.
2. Imposta il topic `status-dormant`.
3. Segnala il repository per l'archiviazione. Archiviare è reversibile con `gh repo unarchive`.
