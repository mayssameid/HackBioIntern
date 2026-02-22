# HackBio Internship
# Learning Experience
This stage helped me think more intentionally about how biological data is presented. Writing the technical piece pushed me to explain concepts such as color bias and accessibility in genomics in a way that could be understood by both technical and non-technical audiences. It reinforced the idea that clarity is just as important as correctness when communicating scientific results.

Documenting my work also improved how I approached my analysis. Writing things down forced me to be precise about my reasoning and decisions, making the overall process more organized and easier to follow.

In addition, although I have previous experience with R, it's always refreshing to go back to the basics.

One key lesson from this stage is that good science depends on how well ideas and results are communicated. Whether through code, figures, or writing, clarity and accessibility are essential for meaningful biological research.

# Regarding Stage 3:
# Cell Type Snapshot Explorer (Shiny, minimal scRNA-seq)

## How to run the app

1. Place the following files in the same folder:

   * `app.R`
   * `expression_matrix.csv`
   * `cell_metadata.csv`
   * `umap_coordinates.csv`
The app will launch locally and reproduce the same outputs every time.

## Gene specificity score definition

The gene specificity score is defined as:

**diff = mean_in − mean_out**

Where:

* `mean_in`: average expression of the gene in the selected cell type
* `mean_out`: average expression of the gene in all other cell types

A higher diff value indicates that the gene is more specific to the selected cell type.

## Marker gene selection

The marker gene is selected deterministically using:

1. The gene with the maximum **diff** value.
2. If there is a tie, the gene with the higher **det_in** (detection rate inside the selected cell type) is chosen.

This ensures consistent and reproducible marker gene identification for UMAP coloring.




