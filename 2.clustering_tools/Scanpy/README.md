https://scanpy.readthedocs.io/en/stable/
Scanpy – Single-Cell Analysis in Python
Scanpy is a scalable toolkit for analyzing single-cell gene expression data built jointly with anndata. It includes preprocessing, visualization, clustering, trajectory inference and differential expression testing. The Python-based implementation efficiently deals with datasets of more than one million cells.

Key Contributors

anndata graph | scanpy graph | ☀ = maintainer

Isaac Virshup: lead developer since 2019 ☀

Gökcen Eraslan: developer, diverse contributions ☀

Sergei Rybakov: developer, diverse contributions ☀

Fidel Ramirez: developer, plotting ☀

Giovanni Palla: developer, spatial data

Malte Luecken: developer, community & forum

Lukas Heumos: developer, diverse contributions

Philipp Angerer: developer, software quality, initial anndata conception ☀

Alex Wolf: lead developer 2016-2019, initial anndata & scanpy conception

Fabian Theis & lab: enabling guidance, support and environment

Discuss usage on Discourse and development on GitHub.

Get started by browsing tutorials, usage principles or the main API.

Follow changes in the release notes.

Find tools that harmonize well with anndata & Scanpy via the external API and the ecosystem page.

Check out our contributing guide for development practices.

Consider citing Genome Biology (2018) along with original references.

News
Scanpy hits 100 contributors! 2022-03-31
100 people have contributed to Scanpy’s source code!

Of course, contributions to the project are not limited to direct modification of the source code. Many others have improved the project by building on top of it, participating in development discussions, helping others with usage, or by showing off what it’s helped them accomplish.

Thanks to all our contributors for making this project possible!

New community channels 2022-03-31
We’ve moved our forums and have a new publicly available chat!

Our discourse forum has migrated to a joint scverse forum (discourse.scverse.org).

Our private developer Slack has been replaced by a public Zulip chat (scverse.zulipchat.com).

Toolkit for spatial (squidpy) and multimodal (muon) published 2022-02-01
Two large toolkits extending our ecosystem to new modalities have had their manuscripts published!

Muon, a framework for multimodal has been published in Genome Biology.

Squidpy a toolkit for working with spatial single cell data has been published in Nature Methods.

(past news)

Latest additions
Version 1.9
1.9.1 2022-04-05
Bug fixes

normalize_total() works when Dask is not installed PR 2209 R Cannoodt

Fix embedding plots by bumping matplotlib dependency to version 3.4 PR 2212 I Virshup

1.9.0 2022-04-01
Tutorials

New tutorial on the usage of Pearson Residuals: → tutorial: tutorial_pearson_residuals J Lause, G Palla

Materials and recordings for Scanpy workshops by Maren Büttner

Experimental module

Added scanpy.experimental module! Currently contains functionality related to pearson residuals in scanpy.experimental.pp PR 1715 J Lause, G Palla, I Virshup. This includes:

normalize_pearson_residuals() for Pearson Residuals normalization

highly_variable_genes() for HVG selection with Pearson Residuals

normalize_pearson_residuals_pca() for Pearson Residuals normalization and dimensionality reduction with PCA

recipe_pearson_residuals() for Pearson Residuals normalization, HVG selection and dimensionality reduction with PCA

Features

filter_rank_genes_groups() now allows to filter with absolute values of log fold change PR 1649 S Rybakov

_choose_representation now subsets the provided representation to n_pcs, regardless of the name of the provided representation (should affect mostly neighbors()) PR 2179 I Virshup PG Majev

scanpy.external.pp.scrublet() (and related functions) can now be used on AnnData objects containing multiple batches PR 1965 J Manning

Number of variables plotted with pca_loadings() can now be controlled with n_points argument. Additionally, variables are no longer repeated if the anndata has less than 30 variables PR 2075 Yves33

Dask arrays now work with scanpy.pp.normalize_total() PR 1663 G Buckley, I Virshup

embedding_density() now allows more than 10 groups PR 1936 A Wolf

Embedding plots can now pass colorbar_loc to specify the location of colorbar legend, or pass None to not show a colorbar PR 1821 A Schaar I Virshup

Embedding plots now have a dimensions argument, which lets users select which dimensions of their embedding to plot and uses the same broadcasting rules as other arguments PR 1538 I Virshup

print_versions() now uses session_info PR 2089 P Angerer I Virshup

Ecosystem

Multiple packages have been added to our ecosystem page, including:

decoupler a for footprint analysis and pathway enrichement PR 2186 PB Mompel

dandelion for B-cell receptor analysis PR 1953 Z Tuong

CIARA a feature selection tools for identifying rare cell types PR 2175 M Stock

Bug fixes

Fixed finding variables with use_raw=True and basis=None in scanpy.pl.scatter() PR 2027 E Rice

Fixed scanpy.external.pp.scrublet() to address issue 1957 FlMai and ensure raw counts are used for simulation

Functions in scanpy.datasets no longer throw OldFormatWarnings when using anndata 0.8 PR 2096 I Virshup

Fixed use of scanpy.pp.neighbors() with method='rapids': RAPIDS cuML no longer returns a squared Euclidean distance matrix, so we should not square-root the kNN distance matrix. PR 1828 M Zaslavsky

Removed pytables dependency by implementing read_10x_h5 with h5py due to installation errors on Windows PR 2064

Fixed bug in scanpy.external.pp.hashsolo() where default value was set improperly PR 2190 B Reiz

Fixed bug in scanpy.pl.embedding() functions where an error could be raised when there were missing values and large numbers of categories PR 2187 I Virshup

