# bingen_updates

Feed de actualizaciones de Sparkle y artefactos publicados de [BinGen](https://github.com/hiyuno/Bingen).

Este repositorio está separado del código de BinGen a propósito: **Bingen puede ser
privado** sin romper las actualizaciones automáticas, porque Sparkle solo necesita
que este repo (y su GitHub Pages) sigan siendo públicos.

## Qué vive aquí

- `appcast.xml` — el feed RSS que Sparkle consulta (`SUFeedURL` en el `Info.plist` de
  BinGen apunta a `https://hiyuno.github.io/bingen_updates/appcast.xml`).
- `index.html` — página mínima servida en la raíz de GitHub Pages.
- [Releases](https://github.com/hiyuno/bingen_updates/releases) — los `.dmg` firmados
  y notarizados de cada versión (`vX.Y.Z`), subidos con `gh release create`.

## Qué NO vive aquí

El código fuente de BinGen. Ese sigue en
[`hiyuno/Bingen`](https://github.com/hiyuno/Bingen), que puede ser un repo privado.

## Cómo se actualiza

`scripts/release.sh` (en el repo de BinGen) actualiza `appcast.xml` en un clon local
de este repo y al final **imprime** (no ejecuta) los comandos de `gh release create`
y `git commit && git push` para publicar aquí. Nunca publica automáticamente.

## Setup único de este repo

1. `git push -u origin main` la primera vez (ver `scripts/bootstrap-updates-repo.sh`).
2. En Settings → Pages → "Build and deployment" → Source: **GitHub Actions**
   (no "Deploy from a branch"). El workflow `.github/workflows/pages.yml` despliega
   la raíz de este repo.
