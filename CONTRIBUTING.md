# Contribuire ai repository bitmama-reply

Regole valide per tutti i repository dell'organizzazione che non definiscono le proprie.

## Metadati obbligatori del repository

Ogni repository deve avere, entro il primo giorno di vita:

| Cosa | Dove | Esempio |
| --- | --- | --- |
| Descrizione in una riga | campo *Description* | `Portale clienti — Next.js + CMS headless` |
| Cliente | topic `client-<slug>` | `client-nome-cliente` |
| Stack | topic `stack-<slug>` (uno o più) | `stack-nextjs` `stack-wordpress` |
| Stato | topic `status-<slug>` | `status-active`, `status-maintenance`, `status-dormant` |
| Referente | `CODEOWNERS` | `* @nome.cognome` |

Questi metadati alimentano l'[indice dei progetti](https://github.com/bitmama-reply) sulla home dell'organizzazione. Un repository senza `client-*` compare come "Senza cliente assegnato".

### Valori ammessi

`status-*` è un **insieme chiuso** di tre valori:

| Topic | Significato |
| --- | --- |
| `status-active` | in sviluppo adesso |
| `status-maintenance` | vivo ma senza sviluppo in corso: interventi su richiesta, manutenzione contrattuale |
| `status-dormant` | chiuso o fermo, candidato ad archiviazione |

Qualsiasi altro valore viene ignorato. Se `status-*` manca, lo stato è dedotto dall'ultimo push: attivo entro 90 giorni, in manutenzione entro un anno, dormiente oltre. Il topic esplicito serve quando la deduzione sbaglia — un progetto in manutenzione contrattuale che non riceve commit da mesi risulterebbe altrimenti dormiente.

`client-*` e `stack-*` sono invece **aperti**: si aggiungono man mano che arrivano clienti e tecnologie. Per questo l'elenco dei valori già in uso non sta qui, dove invecchierebbe, ma in fondo all'[indice dei progetti](https://github.com/bitmama-reply), rigenerato ogni settimana dai repository stessi. **Guardalo prima di inventare un valore nuovo**: `stack-nextjs` e `stack-next` per GitHub sono due etichette diverse e spezzano i raggruppamenti dell'indice.

Un cliente, uno slug: `client-hera` copre tutte le società del gruppo, non se ne apre uno per controllata. Per lo stack si etichetta ciò che serve a ritrovare il repo — framework, CMS, linguaggio se dominante — non ogni dipendenza del `package.json`.

Vincoli di forma imposti da GitHub: solo minuscole, cifre e trattini, massimo 50 caratteri per topic, massimo 20 topics per repository.

## README

Usa `README-template.md` di questo repository come base. Le cinque sezioni non negoziabili sono: cosa fa, ambienti, come si avvia in locale, come si rilascia, chi lo segue.

## Branch e commit

- `main` è protetto: si entra solo via pull request.
- Branch di lavoro: `feat/<breve-descrizione>`, `fix/<breve-descrizione>`, `chore/<breve-descrizione>`.
- Messaggi di commit in [Conventional Commits](https://www.conventionalcommits.org/): `feat:`, `fix:`, `chore:`, `docs:`, `refactor:`.

## Decisioni tecniche

Le scelte che qualcuno rimetterà in discussione fra un anno vanno in `docs/adr/`, un file per decisione, formato `NNNN-titolo-in-kebab-case.md`:

```markdown
# 0003 — Passaggio a un CMS headless

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
