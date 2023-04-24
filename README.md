
<!-- README.md is generated from README.Rmd. Please edit that file -->

# psymetadata

<!-- badges: start -->
<!-- badges: end -->

This data package provides open datasets from meta-analyses from
different areas in psychological science.

## Installation

<!-- You can install the released version of glaxo from [CRAN](https://CRAN.R-project.org) with: -->
<!-- ``` r -->
<!-- install.packages("glaxo") -->
<!-- ``` -->

You can install released version of `psymetadata` from
[CRAN](https://CRAN.R-project.org) with:

``` r
install.packages("psymetadata")
```

If you want to install the most recent development version from GitHub,
use the following code:

``` r
# install.packages("devtools")
devtools::install_github("josue-rodriguez/psymetadata")
```

## Adding a dataset

If you’d like to contribute a dataset to this package please do the
following steps:

### 1)

Clone the repository to your local machine

### 2)

Clean your dataset so it is of type `data.frame` and has at least the
following columns:

- `study_id`: unique id for study
- `es_id`: unique id for effect size (if applicable)
- `yi`: effect size
- `vi`: variance of effect size

Column names should follow snake case formatting. This can easily be
done by calling `janitor::clean_names()` on your data set.

Feel free to include as many moderators or additional columns as you
would like.

### 3)

Assign your dataset to an object with the format `[firstauthor][year]`
and save it to the `data` folder with the format
`[firstauthor][year].rda`, e.g.

``` r
curry2015 <- cleaned_dataset
save(curry2015, file = "data/curry2015.rda")
```

where `curry2015` is a dataset originally collected from the publication
Curry, Thompson, and Green (2015)

### 4)

Add a bibtex reference to the `inst/REFERENCES.bib` file. This can be
easily obtained with a citation manager (e.g., Zotero) or with Google
scholar

### 5)

Document your dataset at the bottom of the `R/data.R` file.

The documentation should roughly follow this format:

    #' @title [Title]
    #'
    #' @description Results from [# of studies] studies, including [# of effect sizes] effect 
    #' sizes ([type of effect size]), on [short description of studies] \insertCite{[cite key]}{psymetadata}.
    #'
    #' @format A data frame with [# of rows] rows and [# of columns] variables:
    #'
    #' * \code{yi}: [description]
    #' * \code{vi}: [description]
    #' * \code{study_id}: [description]
    #' * \code{es_id}: [description]
    #' * \code{moderator1}: [description]
    #' * \code{moderator2}: [description]
    #'
    #'
    #' @md
    #'
    #' @details Further details can be found at \href{[link]}{[link]}
    #'
    #' @usage data("[dataset]")
    #'
    #' @references
    #' \insertAllCited{}
    "[dataset]"

- Take a look at the `data.R` file for more examples

### 6)

Submit a pull request
