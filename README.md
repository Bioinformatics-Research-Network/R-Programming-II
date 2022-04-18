# R Programming II

<!---
Update the badge below as the version changes
-->

[![](https://img.shields.io/static/v1?label=Classroom&message=Launch&color=blue&logo=GitHub)](https://classroom.github.com/a/I0x9GSYa)
![](https://img.shields.io/static/v1?label=Version&message=0.0.1a&color=green)

**Purpose**: This skill assessment will test your intermediate R programming skills.

**Pre-requisites**: *Required*: [R Programming I](https://github.com/Bioinformatics-Research-Network/R-Programming-I); *Suggested*: [RMarkdown basics]()


## Background

After you completed the tasks your supervisor gave you in R Programming I, you get a call from HR. Apparently, your functions were so useful that your been promoted from a Bioinformtics Assistant to Bioinformatics Programer 🚀. Your first task will be to turn your `utils.R` script into a package, `BioUtils`, for the whole bioinformatics team to use 🎯. The package should contain all the functions you wrote in `utils.R`, but properly formatted as an R package and well-documented. This will enable your colleagues to easily install your package and use the functions contained within!

Users will use your package like so:

```R
library(BioUtils)

cancer <- "ATCGCATACGA"
normal <- "ATCCCAGATGA"

protein_variant(cancer, normal)
```

## Requirements

**NOTE**: Due to naming conventions in R packages, it is a very good idea to clone this github repository with the name `BioUtils` specified for the output directory:

```shell
git clone <link_to_repo> BioUtils
```



### Automated testing / checking

Prior to releasing the package, your new supervisor will make sure that everything works correctly and that it is well-formatted/documented. She will deploy a bot to run automated checks on your package -- they should produce no errors, warnings, or notes.

<details>
<summary>Automated checks</summary>

The bot will initiate an `R v4.1.2` session and install `BioUtils` package by running:

```R
devtools::build()
```

Then it will test the package by running:

```R
devtools::test()
```

Next, it will run CRAN checks:

```R
devtools::check(cran = TRUE, error_on="note")
````

Next, it will check the style of the package using `lintr` from the linux command line:

```shell
Rscript -e "errors <- lintr::lint_package(); print(errors); quit(save = 'no', status = length(errors))"
```

Finally, it will ensure that your vignette(s) can be successfully built from the linux command line (test this in R by running `devtools::build_vignettes()`):

```shell
Rscript -e "if (is.null(devtools::build_vignettes())) quit(save = 'no', status = 1)"
```

</details>

<br>

### Manual inspection

If the bot checks are successful, your supervisor will manually inspect the package to ensure that the documentation is clear and easy to follow.

To aid her in this effort, you are expected to provide a vignette which outlines how the package works. See a completed example [here](https://bioinformatics-research-network.github.io/R-Programming-II/bioutils_quickstart.html).

The easiest way to create one is the run:

```R
usethis::use_vignette(name = "bioutils_quickstart", title = "BioUtils Quickstart")
```

This will create an [RMarkdown](https://rmarkdown.rstudio.com/) document, `vignettes/bioutils_quickstart.Rmd`. Edit this document to create your vignette. 

Then, build your vignette like so:

```R
devtools::build_vignettes()
```

This will create an HTML document in the following location: `doc/bioutils_quickstart.html`. This is the HTML (user-friendly) vignette.

## Additional resources

To learn about building and documenting R packages, visit the following link: [R packages book](https://r-pkgs.org/)

The easiest way to complete this assignment is to make heavy usage of the `usethis` R package: [link](https://usethis.r-lib.org/). For example, it is strongly recommended to begin this task by running `usethis::create_package()`. When adding new datasets to the package, it is recommended to run `usethis::use_data_raw()` to initialize them.

