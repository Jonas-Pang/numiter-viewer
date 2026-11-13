# numiter-viewer

Interactive viewer for the random-phase propagation experiment on the [SplitLohmann](https://github.com/Image-Science-Lab-cmu/SplitLohmann) display simulation.

**Live page:** https://jonas-pang.github.io/numiter-viewer/

The simulator approximates the incoherent OLED display by averaging the retinal intensity of `sim.num_iter` coherent propagations, each started from an independent random phase. More propagations mean less speckle and more compute. The page shows six photos in color at N = 1, 5, 10, 20, 30, 40, 50, 60, 70 and at seven eye-focus settings spanning the depths in each photo.

- Slider 1: number of averaged propagations N (`sim.num_iter`).
- Slider 2: eye focus, far to near.
- Left: the whole scene, every 2.5th pixel with no smoothing, so the grain is as strong as at full size. The blue box marks the region shown on the right at full resolution.
- Right panel: PSNR, SSIM and compute time for the selected N, measured in a MATLAB run of the original code.

## Data

- Images: Python port of `simulation.m` / `render.m` (same propagation steps), R, G and B simulated separately as with `flags.color = true` (the code uses one wavelength for all three), mode 1 (5 µm grid). The port agrees with the MATLAB code to within 0.07 dB PSNR.
- Metrics: MATLAB Online run of the original SplitLohmann code on the same photos (green channel), reference N = 280, mean over a subject focus and a background focus.
- Photos and depth maps: group photos, depth maps scaled to 0 to 4 diopters (gray x 4/254).
