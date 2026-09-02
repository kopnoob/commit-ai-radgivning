# AI-rådgivning — Commit AS

Tjenestebeskrivelse for Commits AI-rådgivning, bygget rundt selskapets egen
lønnskjøring som case.

**Publisert:** https://kopnoob.github.io/commit-ai-radgivning/

| Fil | Hva |
|---|---|
| `index.html` | Dokumentet. Selvstendig — CSS og logoer er bakt inn, kun Google Fonts hentes eksternt. |
| `ai-radgivning.pdf` | Samme dokument som 6 siders A4. |

## Redigering

Kilden ligger **ikke** her, men i OneDrive under
`Salg Commit/AI-rådgivning/ai-radgivning.src.html`, sammen med byggescriptene
(`build.py`, `figurer.py`, `artifact.py`). De er avhengige av Commits felles
designsystem, som ikke er offentlig.

Slik oppdaterer du denne siden:

```bash
cd "…/Salg Commit/AI-rådgivning"
python3 figurer.py && python3 build.py
node "…/Designsystem Commit/tools/render-pdf.js" ai-radgivning.html
cp ai-radgivning.html <dette-repoet>/index.html
cp ai-radgivning.pdf  <dette-repoet>/
```

Skissene er SVG generert av `figurer.py`. Kjør
`Designsystem Commit/tools/sjekk-figurer.mjs` før publisering — den måler hver
tekst mot boksen sin og fanger overflow.
