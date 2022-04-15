# R Programming II

After you completed the tasks your supervisor gave you in R Programming I, you get a call from HR. apparently, your functions were so useful that your been promoted from a Bioinformtics Assistant to Bioinformatics Programer. Your first task will be to turn your `utils.R` script into a package, `BioUtils`. The package should contain all your functions, but well-documented so that people understand how to use them. 

Your collleagues will install this package by navigating to your package's folder and running:


```bash
R command build
```

Then the users will use your package like so:

```R
library(BioUtils)

cancer <- "ATCGCATACGA"
normal <- "ATCCCAGATGA"

protein_variant(cancer, normal)


```

To learn about building packages, visit the following link: [R packages book](https://r-pkgs.org/)

To be accepted, you package should pass all the tests in the `tests/` folder and the package must pass CRAN checks. 


Within R Studio, there ar  a variety of tools to aid you in building your package, such as. 




