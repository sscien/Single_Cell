Pitfalls of trajectory analysis
The resulting difficulty in determining distinct lineage relationships between complex human T cell populations in vivo has spurred use of differentiation trajectory algorithms to develop a biological framework for tumor-infiltrating lymphocyte differentiation. Key methods of this kind include trajectory analysis using pseudotime and RNA velocity to infer differentiation pathways among cells analyzed by single-cell RNA sequencing (scRNA-seq) (La Manno et al., 2018; Trapnell et al., 2014). Although these methods can be useful for hypothesis generation, they are not substitutes for experimental determination of lymphocyte differentiation trajectories and may lead to erroneous results even in relatively simple experiments.
As an example, to determine the differentiation pathways of virus-specific CD8+ T cells, (Kurd et al., 2020) transferred P14 cells—TCR-transgenic CD8+ T cells specific for a LCMV epitope—to wild-type mice. After infection of recipient mice with the acute strain of LCMV Armstrong, the authors isolated donor P14 cells at various time points and performed scRNA-seq (Figures 2A and 2B ). Because the stage of differentiation and time after antigen exposure are known for every cell in this experiment, this is an excellent dataset to compare the ground truth (real time) with inferred pseudotime. We re-analyzed their dataset, performing dimensionality reduction of sequenced cells with uniform manifold approximation and projection (UMAP) and trajectory inference with Slingshot (McInnes et al., 2018; Street et al., 2018). The actual, real-time trajectory of CD8+ T cell differentiation followed a clockwise pattern in UMAP space (Figure 2C), whereas trajectory inference predicted the opposite differentiation pathway as determined by biological experimentation: naive cells were predicted to differentiate into memory cells first, followed by subsequent transition into late and early effectors (Figure 2D).

Figure 2Inference of a reverse differentiation trajectory from scRNA-seq data
Hide caption
(A) TCR-transgenic CD8+ T cells were transferred to mice that were subsequently infected with LCMV Armstrong. At the illustrated time points, cells were sorted and subjected to scRNA-seq.
(B) Expression of T cell differentiation markers at the indicated time points.
(C) UMAP projection of sequenced cells, with an arrow indicating the actual cell differentiation trajectory.
(D) Identical UMAP projection with inferred trajectories.
(E) Heatmap of T cell differentiation marker expression, with cells in real-time order.
(F) Heatmap of T cell differentiation marker expression, with cells in pseudotime order. Raw data are from Kurd et al., 2020.
Code and data to reproduce the scRNA-seq analysis are available on Mendeley Data (https://doi.org/10.17632/3dvt79c7yt.1).

![image](https://user-images.githubusercontent.com/80489022/197236669-959aa279-481b-4c49-b2a5-f09b7b228780.png)
