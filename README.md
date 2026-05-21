# SymmDiff: Symmetry-Guided Diffusion for Fracture Localization in Pelvic Radiographs

**<a href="https://itsabdulrahman.github.io/">Abdul Rahman¹</a>,
<a href="https://scholar.google.com/citations?user=UngixbEAAAAJ&hl=en"/>Afnan Ghafoor²</a>,
<a href="https://scholar.google.com/citations?user=maY0q9IAAAAJ&hl=en"/>Bumshik Lee¹</a>**

¹ Energy AI Track, Korea Institute of Energy Technology (KENTECH), South Korea \
² Information and Communication Engineering Department, Chosun University, South Korea

Corresponding author: Bumshik Lee \<bslee@kentech.ac.kr\>


**🌟 Early accepted at MICCAI 2026 main conference**

## Abstract

Unsupervised anomaly detection (UAD) offers a promising direction for fracture analysis where abnormal annotations are scarce, yet pelvic X-ray fracture detection remains exceptionally challenging due to overlapping anatomy, projection artifacts, and the inherently asymmetric presentation of fracture patterns. We introduce SymmDiff, a symmetry-aware diffusion framework that embeds contralateral anatomical consistency directly into the generative correction process, mirroring the clinical practice of bilateral comparison. By pairing anatomically corresponding left-right regions and enforcing symmetry-consistent reconstruction during diffusion, SymmDiff generates a normal-corrected radiograph that selectively suppresses fracture-induced asymmetries while preserving global anatomical structure, enabling precise fracture localization through residual discrepancies between the input image and its symmetry-corrected counterpart. Extensive evaluations on pelvic radiographs spanning subtle to severe fractures show that SymmDiff consistently outperforms existing anomaly-detection baselines, highlighting the effectiveness of symmetry-guided generative modeling for reliable fracture localization in clinical imaging.

## Code
Coming soon.
