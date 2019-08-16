library(stats)
library(colorout)
Sys.setenv(TZ = "Australia/Sydney")
options(

  # Default CRAN mirror
  repos = c(CRAN = "https://cran.rstudio.com"),

  # Column width of console
  width = 76,

  # usethis options
  usethis.full_name = "David Wilkins",
  usethis.description = list(
    `Authors@R` = 'person(
      "David",
      "Wilkins",
      email = "david@wilkox.org",
      role = c("aut", "cre")
    )',
    License = "MIT + file LICENSE",
    Version = "0.0.0.9000"
  ),
  usethis.protocol  = "ssh",

  # blogdown options
  blogdown.author = "David Wilkins",
  blogdown.ext = ".Rmd"

)
if (interactive()) {
  suppressMessages(require(devtools))
  suppressMessages(require(usethis))
}
# R will silently ignore the last line of .Rprofile unless it ends with a
# newline
