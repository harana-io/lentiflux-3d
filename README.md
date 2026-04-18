# LentiFlux / 3GX

> Interactive 3D model of a third-generation self-inactivating (SIN) lentiviral vector system carrying a 7 kb therapeutic transgene for solid tumor cell & gene therapy manufacturing.

**Live demo:** https://harana-io.github.io/lentiflux-3d/

![Third-Gen Lentiviral Vector](https://img.shields.io/badge/lentivirus-3rd_gen_SIN-00e5ff) ![Payload](https://img.shields.io/badge/transgene-7.0_kb-ffb14d) ![Stack](https://img.shields.io/badge/stack-three.js-7c5cff)

---

## What it shows

Five interactive scenes walking through the full vector system. Click the bottom nav or press `1`–`5`.

| # | Scene | Content |
|---|-------|---------|
| 01 | **Producer Cell** | HEK293T + 4-plasmid 3rd-gen system (transfer · gag/pol · Rev · VSV-G), scaled to real backbone sizes |
| 02 | **Transfer Plasmid** | Circular ~13.5 kb pLenti vector — packaged cassette *vs.* bacterial backbone |
| 03 | **Packaging Capacity** | EF1α (~10.7 kb, over limit) *vs.* EFS (~9.7 kb, marginal) + titer-decay curve |
| 04 | **Mature Virion** | Pleomorphic envelope · ~88 VSV-G trimers · p17 matrix · conical p24 capsid · DIS-linked (+)ssRNA dimer |
| 05 | **Lifecycle** | (+)ssRNA → RT-mediated ΔU3 duplication → integrated SIN provirus → effector cell (CAR-T / TCR-T / NK) |

## Scientific notes

- **Tat-independent transcription** via chimeric `RSV/CMV-R-U5` 5′ LTR (Dull et al. 1998).
- **SIN LTR** — the 3′ ΔU3 is copied to both LTRs post-RT, silencing LTR-driven transcription in the integrated provirus (Zufferey et al. 1998 · Miyoshi et al. 1998).
- **Packaging budget** is a titer *gradient* (~2× decay per kb above ~9.5 kb), not a hard cutoff (Kumar et al. 2001 · al Yacoub et al. 2007).
- **VSV-G pseudotyping** confers pan-tropic LDL-R-mediated entry (Finkelshtein et al. 2013).

## Tech

- Three.js `r160` via ES modules (unpkg CDN) — no build step, single HTML file.
- UnrealBloomPass for glow, ACES tone mapping, `MeshPhysicalMaterial` for glassmorphic envelopes.
- Pleomorphic geometries via procedural noise displacement on `SphereGeometry`.
- CSS3 glassmorphism HUD with per-scene info cards, mechanism blocks, and citations.

## Run locally

```bash
# just open the file — no build, no dependencies
open index.html
```

Or serve it:

```bash
python3 -m http.server 8000
# → http://localhost:8000
```

## Disclaimer

Figure is designed for presentation and education. Spike density, capsid hexamer counts, and molecular proportions are stylized for legibility. For quantitative claims, refer to the cited primary literature.

## License

MIT — do what you want. Attribution appreciated.
