# norton-tanzarella-cms-contract

Contratto unico del CMS Norton Tanzarella: schemi Zod, registry delle pagine fisse, `zodToFieldMeta` per il backoffice. Lo importano backend, web e backoffice.

Solo la parte di questo repo. Il metodo sta nelle regole globali del kit; il progetto nella casa, `upstudioit/norton-tanzarella-docs`.

## Stack e comandi

- Stack: TypeScript, Zod, tsup, Vitest. pnpm.
- Build: `pnpm build` (`pnpm install` lancia `prepare`, che usa il `dist` già pronto e lancia tsup solo se manca)
- Test: `pnpm test`, `pnpm typecheck`
- Ramo base delle PR: `main`
- Rilascio: nuova `version` in `package.json`, tag `v0.x.x`, poi il pin `github:antoniop88/norton-tanzarella-cms-contract#v0.x.x` aggiornato in backend, web e backoffice. Il repo ora è `upstudioit/norton-tanzarella-cms-contract`: il vecchio nome nei pin funziona grazie al rimando di GitHub. Un cambio incompatibile va anche nel changelog della spec e nei `docs/cms.md` dei tre consumer.

## Zona critica

Il lavoro che tocca queste parti segue le regole della zona critica, anche senza etichetta:

- `src/`: ogni schema e il registry. Un cambio incompatibile rompe tre consumer.
- `.github/workflows/`

## Issue, spec e ADR

La riga `- Issue:` la legge uno script del kit: `owner/repo` tra apici inversi, niente altro sulla riga (un punto finale è accettato).

- Issue: `upstudioit/norton-tanzarella-docs`
- Project: nessuno
- Spec: `docs/` in `upstudioit/norton-tanzarella-docs` (estratto per questo repo in [docs/cms.md](docs/cms.md))
- ADR: `adr/` in `upstudioit/norton-tanzarella-docs`

Vincoli del cliente, server e rilascio: nell'`AGENTS.md` di `norton-tanzarella-docs`.
