# START HERE — your first weeks

Welcome, Mohammad. This project is an **SR-Uplift Evidence Pack**: does NextAV super-resolution
improve vegetation-change detection vs raw Sentinel-2, and *where*? Full spec is in the proposal v2.

## Plan (cycle 14 Jun – 3 Sep 2026, 40 hrs/week)

Work the board in order: https://github.com/orgs/NextAV/projects/6

**Week 1 has two gates, in order:**
1. **#1 Environment** — clone, venv, `pip install -r requirements.txt`, `pytest` green.
2. **#2 Pre-register the question + methodology** (do this BEFORE any modelling). One page, Hichem signs off:
   the question is *"WHERE does SR help vegetation-change detection vs raw 10 m Sentinel-2?"* (not "prove SR
   helps"); lock the two arms (raw 10 m vs NextAV SR), the **primary eval at fixed 10 m**, the metrics, and the
   adversarial AOI set.
3. **#3 Data pipeline** for both AOIs.

## The two AOIs (open data)

- **Doha green space** (CityView/Earthna) — Sentinel-2 + ESA WorldCover.
- **Montiferru, Sardinia** (TERNA corridor) — the July-2021 wildfire near TERNA's lines; reference =
  the **EFFIS / Copernicus EMS** burned-area perimeter (clip to the official perimeter; don't hand-draw a box).
  EFFIS: https://forest-fire.emergency.copernicus.eu/ · Copernicus EMS: https://mapping.emergency.copernicus.eu/

## The one rule that makes the benchmark valid

**Score at fixed 10 m.** Run the task on both arms; for the SR arm, downsample the prediction back to
10 m and score against the reference. Never validate a 1 m prediction against 10 m labels — that result
is invalid. Fine-feature 1 m gains are a *separate, small* hand-validated supplement.

## Resources
- PyTorch — https://pytorch.org/tutorials/ · TorchGeo — https://torchgeo.readthedocs.io/
- segmentation-models-pytorch — https://github.com/qubvel-org/segmentation_models.pytorch
- Sentinel-2 STAC — https://github.com/Element84/earth-search · ESA WorldCover — https://esa-worldcover.org/
- Burn index (NBR/dNBR) — https://un-spider.org/advisory-support/recommended-practices/recommended-practice-burn-severity

## How to get help
- Comment on your task issue, or open a `question: ...` issue. For anything blocking, email Hichem.

## Guardrails
- Open data only; read-only on the SR sample tiles; no SR model training. Internal benchmark — never in a customer deliverable.
