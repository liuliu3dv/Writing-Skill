---
name: research-paper-reading
description: Read and explain research papers in depth from the original PDF, figures, captions, tables, and equations. Use for paper deep dives, figure walkthroughs, and cross-checking a paper's method or experiments against released source code and configurations.
---

# Research Paper Reading

## Establish the sources

Use the supplied paper PDF or obtain it from the publisher, proceedings, or official preprint record. Record the paper version and use the matching supplement or official HTML where available. Prefer the PDF for figure numbering and layout. When supplied and published versions differ, identify the version used and label any evidence drawn from another version.

## Read the original figures and captions

1. Locate the figure, its caption, and the paragraphs that cite it. Visually inspect the PDF page. Render the page or crop the original figure if you need to display it. Rendering preserves vector graphics, text, and panels that may be missing from a raster image extracted from the PDF.
2. Check that the crop preserves the relevant panels, labels, axes, and legend. Show the original figure when possible, alongside its figure and panel numbers, PDF page or official HTML anchor, and the matching caption or a clearly labeled caption summary. For a single-panel crop, identify the panel explicitly.
3. If PDF rendering or extraction fails, use the same-version official HTML figure and caption. If neither source can be verified, say what is unavailable, link to the closest verified paper location, and continue with evidence you can inspect.
4. Never use image search results, lookalike images, or third-party redraws as paper figures. Label any explanatory sketch as a schematic created for the walkthrough and cite the source it interprets.

Walk through the relevant panels, tracing inputs, intermediate representations, outputs, and how the blocks connect. For architecture figures, distinguish training and inference paths. For result plots, read the axes, units, legend, and uncertainty before interpreting the trend. Use the caption and nearby text to resolve ambiguities, and label any remaining interpretation.

## Cross-check the implementation

Check the supplied repository or look for the official release in the paper, supplement, or project page. Confirm that the repository and subdirectory correspond to the paper. If no release can be verified, report that limit. Use the paper's release tag or commit when available. Otherwise pin the inspected commit and state whether its correspondence to the paper release is known. Record the repository and link to commit-pinned files and lines.

Start with the relevant training, inference, or evaluation entry point. Follow the active calls and selected configuration through the model, data transforms, losses, or metric code that bears on the claim. Check the options and overrides that select that behavior. A module or default value alone does not establish which path produced a reported result.

For each important check, pair the paper location with the code location and state whether the inspected code agrees, differs, or leaves the claim unresolved. Separate a confirmed implementation difference from a possible version mismatch. If code, configuration, checkpoints, or run records are missing, specify which verification they prevent. Distinguish static inspection from a run actually performed and from independent reproduction of a paper result.

## Check the experiments and report the evidence

- Read the original tables, captions, footnotes, and evaluation protocol. Preserve table or figure numbers, benchmark and split, metric and units, baseline, and ablation setting when reporting results. Check that compared values use compatible settings and distinguish percentage-point gains from relative gains.
- Explain the problem and contribution, then connect the relevant figures, equations, implementation paths, and experiments. Scale the coverage to the user's question and answer in the user's language.
- Attribute each central claim to the paper, the inspected implementation, or your own analysis. Put source links next to the corresponding claims and state what remains unverified. Treat author-reported results as such unless you independently reproduced them.
