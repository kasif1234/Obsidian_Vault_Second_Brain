==Objectives:==  Determine _where_ (which conditions/locations) NextAV's super-resolution actually improves vegetation-change detection over raw 10 m Sentinel-2 — not whether SR is universally better, but mapping out its specific zones of benefit (and failure) using two real AOIs (Doha green space, Montiferru wildfire), scored fairly at a fixed 10 m grid for both arms.

==My analysis==:
"Arms" is just experiment-design language for **the two things you're comparing against each other**, run side-by-side on identical inputs:

- **Arm A (raw):** Sentinel-2 imagery at native 10 m → vegetation-change detection directly on it.
- **Arm B (SR):** Same Sentinel-2 imagery, first upscaled by NextAV's SR model to 1 m → vegetation-change detection on the sharpened version, then downsampled back to 10 m for scoring.

Same task, same AOIs, same reference labels — the only thing that differs between the two "arms" is whether SR sits in the pipeline or not. That isolation is what lets you say "SR caused this difference" rather than "something changed, not sure what."
![[Pasted image 20260622130556.png]]

![[Pasted image 20260622130621.png]]