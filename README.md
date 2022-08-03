# R Programming II <img src="https://api.badgr.io/public/badges/h3lCNmoHRjmqNI5D5Q6a-g/image" align="right" alt="logo" width="240" style = "border: none; float: right;">

[![](https://img.shields.io/static/v1?label=Language&message=R&color=%23276DC2)](https://brnteam.notion.site/e8c045b812d842f8bca8e339d22c38ad?v=6245e8becaa641bcafd276e5d910e402)
[![](https://img.shields.io/static/v1?label=Type&message=Software&color=darkgoldenrod)](https://brnteam.notion.site/e8c045b812d842f8bca8e339d22c38ad?v=6245e8becaa641bcafd276e5d910e402)
[![](https://img.shields.io/static/v1?label=Version&message=0.0.2a&color=purple)](https://brnteam.notion.site/e8c045b812d842f8bca8e339d22c38ad?v=6245e8becaa641bcafd276e5d910e402)
[![](https://img.shields.io/static/v1?label=Lifecycle&message=experimental&color=red)](https://brnteam.notion.site/e8c045b812d842f8bca8e339d22c38ad?v=6245e8becaa641bcafd276e5d910e402)

**Purpose**: To test your fundamental R package development skills. 

**Pre-requisites**: *Required*: [R Programming I](https://github.com/Bioinformatics-Research-Network/R-Programming-I) 

# Instructions

The following instructions describe the [requirements](#requirements) to complete this task and earn the R Programming II badge 🏆. They also provide [guidance](#guidance) to help you along the way. 

A few things to keep in mind:

1. Please remember at all times to abide by the [BRN Code of Conduct](https://docs.google.com/document/d/1q06RJbIsyIzLC828A7rBEhtfkujkj9kx7Y118AaWASA/edit?usp=sharing) and [Academic Honesty Policy](https://docs.google.com/document/d/1-Xoko7VDr0lK7olboGQ2CPmEnUTV3WmiDxwQQuGBgiQ/edit). If you notice violations of these policies, please contact codeofconduct@bioresnet.org. 
2. Please remember to [reach out](#getting-help) if you get stuck, find bugs, or even just have a question!

Good luck and have fun! 😊

~ BRN Bot 🤖



## Requirements

**Badge Requirements**:

[![](https://img.shields.io/static/v1?label=Tests&message=Required&color=lightsalmon)](https://brnteam.notion.site/e8c045b812d842f8bca8e339d22c38ad?v=6245e8becaa641bcafd276e5d910e402)
[![](https://img.shields.io/static/v1?label=Linting&message=Required&color=lightsalmon)](https://brnteam.notion.site/e8c045b812d842f8bca8e339d22c38ad?v=6245e8becaa641bcafd276e5d910e402)
[![](https://img.shields.io/static/v1?label=Coverage&message=Not%20required&color=whitesmoke)](https://brnteam.notion.site/e8c045b812d842f8bca8e339d22c38ad?v=6245e8becaa641bcafd276e5d910e402)
[![](https://img.shields.io/static/v1?label=Review&message=Not%20required&color=whitesmoke)](https://brnteam.notion.site/e8c045b812d842f8bca8e339d22c38ad?v=6245e8becaa641bcafd276e5d910e402)


**Testing environment**:

[![](https://img.shields.io/static/v1?label=Runs%20on&message=Ubuntu%2022.04%20LTS&color=%235e2750)](https://brnteam.notion.site/e8c045b812d842f8bca8e339d22c38ad?v=6245e8becaa641bcafd276e5d910e402)
[![](https://img.shields.io/static/v1?label=R-Version&message=4.2.0&color=cornflowerblue)](https://brnteam.notion.site/e8c045b812d842f8bca8e339d22c38ad?v=6245e8becaa641bcafd276e5d910e402)
[![](https://img.shields.io/static/v1?label=Packages-allowed&message=None&color=lightgray)](https://brnteam.notion.site/e8c045b812d842f8bca8e339d22c38ad?v=6245e8becaa641bcafd276e5d910e402)


**Assessment Premise**: 

**TLDR; Take the functions from [R Programming I](https://github.com/Bioinformatics-Research-Network/R-Programming-I) and turn them into a package called "BioUtils"**

After you completed the tasks your supervisor gave you in [R Programming I](https://github.com/Bioinformatics-Research-Network/R-Programming-I), you get a call from HR. Apparently, your functions were so useful that you have been promoted from a Bioinformatics Assistant to Bioinformatics Associate 🚀. Your first task will be to turn your `utils.R` script into a package, `BioUtils`, for the whole bioinformatics team to use 🎯. The package should contain all the functions you wrote in `utils.R`, but properly formatted as an R package and well-documented. This will enable your colleagues to easily install your package and use the functions contained within!

Users will use your package like so:

```R
library(BioUtils)

cancer <- "ATCGCATACGA"
normal <- "ATCCCAGATGA"

protein_variant(cancer, normal)
```


### Automated testing / checking

Prior to releasing the package, your new supervisor will make sure that everything works correctly and that it is well-formatted/documented. She will deploy a bot to run automated checks on your package -- they should produce no errors, warnings, or notes.

<details>
<summary>Automated checks</summary>

The bot will initiate an `R v4.2.0` session and install `BioUtils` package by running:

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

</details>


## Guidance

Most guidance for this assessment is identical to [R Programming I](https://github.com/Bioinformatics-Research-Network/R-Programming-I), with the following additions:

Due to naming conventions in R packages, it is a very good idea to clone this github repository with the name `BioUtils` specified for the output directory:

```shell
git clone <link_to_repo> BioUtils
```

### Additional resources

To learn about building and documenting R packages, visit the following link: [R packages book](https://r-pkgs.org/)

The easiest way to complete this assignment is to make heavy usage of the `usethis` R package: [link](https://usethis.r-lib.org/). For example, it is strongly recommended to begin this task by running `usethis::create_package()`. When adding new datasets to the package, it is recommended to run `usethis::use_data_raw()` to initialize them.

### Getting help

If you find a bug or get confused, please don't hesitate to contact the BRN Skill Assessment maintainers on the **#help-skill-assessments** Slack channel, and they will assist you. 
