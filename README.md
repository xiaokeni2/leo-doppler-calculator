# LEO Doppler Calculator

A free, single-file web tool that computes **Doppler shift and Doppler rate for LEO satellite passes** from orbit altitude, downlink carrier frequency and maximum (culmination) elevation — the numbers you need to size the tuning span and tracking loop of a satellite ground station receiver, for UHF, S, X or Ku band downlinks.

## Online use

Open the tool directly in your browser (no install, no dependencies, all math runs client-side):

**https://xiaokeni2.github.io/leo-doppler-calculator/**

## What it does

- Inputs: circular-orbit altitude (presets 400 / 550 / 600 / 800 / 1200 km or custom), downlink frequency (presets UHF 437 MHz / S 2200 / X 8100 / Ku 12000 or custom), maximum elevation 5–90°.
- Outputs: maximum Doppler shift at horizon acquisition/loss (with the standard R/r geometry correction), required tuning span, peak Doppler rate at culmination, orbital velocity, period, pass duration, slant range at culmination, and a Doppler-vs-time curve for one pass.
- Comparison table across 400–1200 km altitudes at the selected frequency.
- Standard circular-orbit geometry: v = √(μ/r), μ = 3.986004418×10¹⁴ m³/s²; v_rad = v·R·sinψ/ρ; Δf = f_c·v_rad/c.
- Pure HTML/CSS/JS, dark engineering UI, mobile friendly.

## Formulas

```
r = R_E + h                          R_E = 6371 km
v = √(μ/r),  T = 2π√(r³/μ),  n = v/r
cosψ = [R·cos²E + sinE·√(r² − R²cos²E)] / r      (elevation E)
ρ²   = R² + r² − 2Rr·cosψ
v_rad = v·R·sinψ/ρ   →  v_rad,max = v·(R/r)  at E = 0°
Δf_max = f_c · v·(R/r) / c            (horizon acquisition/loss)
peak dΔf/dt at culmination, pass T = 2(arccos(R/r) − ψ_culm)/n
```

## Usage

1. Pick an altitude preset (or type a custom one), pick a band preset (or a custom MHz), set the maximum elevation of the pass.
2. Read Δf_max and the required ± tuning span, the peak Doppler rate, and check the altitude comparison table.
3. Example: 550 km, 437 MHz, 90° culmination → Δf_max ≈ 10.2 kHz, peak rate ≈ 140 Hz/s, pass ≈ 12 min.

## Related

- [BRIDZA — company overview](https://bridza.com/)
- [BRIDZA RF — oscillators, timing and RF components](https://rf.bridza.com/)
- [Satellite ground station solutions](https://rf.bridza.com/resources/use-cases/satellite-ground-station-solutions.html)
- [Glossary: Doppler shift](https://rf.bridza.com/resources/glossary/doppler.html)

---

More free RF/timing tools: [VSWR Calculator](https://xiaokeni2.github.io/vswr-return-loss-calculator/) · [Phase Noise–Jitter Converter](https://xiaokeni2.github.io/phase-noise-jitter-converter/) · [Clock Tree Jitter Budget Calculator](https://xiaokeni2.github.io/clock-tree-jitter-budget-calculator/) · [Holdover Time Calculator](https://xiaokeni2.github.io/holdover-time-calculator/)

© BRIDZA · Open code, free to use.
