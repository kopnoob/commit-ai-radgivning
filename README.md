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

## Kontorarbeid: «En vanlig måned hos Commit»

Skrytemateriell som viser hvordan Commit automatiserer kontorarbeid i samspill med AI
(oktober 2026). Ligger i `kontorarbeid/`.

**Publisert:** https://kopnoob.github.io/commit-ai-radgivning/kontorarbeid/

| Fil | Hva |
|---|---|
| `kontorarbeid/index.html` | Nettsiden. Tekst og skjermglimt, klar til å flyttes til commit.no. |
| `kontorarbeid/karusell.html` | Kilden til LinkedIn-karusellen, åtte kort i 1080 x 1350. |
| `kontorarbeid/karusell/kort-01.png` … `kort-08.png` | Kortene som bilder. |
| `kontorarbeid/en-vanlig-maned-hos-commit.pdf` | Kortene som PDF (LinkedIn-dokument). |
| `kontorarbeid/linkedin-innlegg.md` | Forslag til innlegget som følger karusellen. |
| `kontorarbeid/karusell/index.html` | Underside til gjennomsyn: kortene som sveip, innleggsteksten og PDF-lenke. |
| `kontorarbeid/commit-style.css`, `glimt.css`, `assets/` | Designsystemet (v2.0 «Punktum.») og de stiliserte skjermglimtene. |

Kortene rendres fra `karusell.html` med Playwright fra `Designsystem Commit/tools/`
(scriptet `render-karusell.mjs` ligger i OneDrive under `Salg Commit/AI-rådgivning/Kontorarbeid/`).
