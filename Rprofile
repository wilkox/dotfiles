library(stats)
Sys.setenv(TZ = "Australia/Adelaide")
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
  usethis.protocol = "https",

  # blogdown options
  blogdown.author = "David Wilkins",
  blogdown.ext = ".Rmd"

)
if (interactive()) {
  suppressMessages(require(devtools))
  suppressMessages(require(reprex))
  suppressMessages(require(usethis))
  suppressMessages(require(colorout))
  setOutputColors(error = c(0, 1), string = 15, verbose = FALSE) 
}
# R will silently ignore the last line of .Rprofile unless it ends with a
# newline
