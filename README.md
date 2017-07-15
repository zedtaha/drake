[![Travis-CI Build Status](https://travis-ci.org/wlandau-lilly/drake.svg?branch=master)](https://travis-ci.org/wlandau-lilly/drake)
[![AppVeyor Build Status](https://ci.appveyor.com/api/projects/status/github/wlandau-lilly/drake?branch=master&svg=true)](https://ci.appveyor.com/project/wlandau-lilly/drake)
[![codecov.io](https://codecov.io/github/wlandau-lilly/drake/coverage.svg?branch=master)](https://codecov.io/github/wlandau-lilly/drake?branch=master)
[![CRAN_Status_Badge](http://www.r-pkg.org/badges/version/drake)](http://cran.r-project.org/package=drake)
[![Licence](https://img.shields.io/badge/licence-GPL--3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0.en.html)
[![minimal R version](https://img.shields.io/badge/R%3E%3D-3.2.0-6666ff.svg)](https://cran.r-project.org/)

![](drake.gif)

# drake - data frames in R for [Make](http://kbroman.org/minimal_make/)

<h1 align="center">
  <img width="200" src="./inst/logo.png" alt="">
</h1>

Drake is a workflow manager and build system that brings you

1. [Reproducibility](https://CRAN.R-project.org/view=ReproducibleResearch).
2. [High-performance computing](https://CRAN.R-project.org/view=HighPerformanceComputing).

# Installation

```r
install.packages("drake") # latest CRAN version
devtools::install_github("wlandau-lilly/drake@v3.1.0", build = TRUE) # latest GitHub release
devtools::install_github("wlandau-lilly/drake", build = TRUE) # development version
```

For `make(..., parallelism = "Makefile")`, Windows users need to download and install [`Rtools`](https://cran.r-project.org/bin/windows/Rtools/).

# Quickstart

```{r}
library(drake)
load_basic_example() # into your workspace.
plot_graph(my_plan) # Graph the workflow.
make(my_plan) # Run the workflow.
make(my_plan) # Check that everything is already up to date.
```

Dive deeper into the built-in examples.

```r
example_drake("basic") # Write the code files.
examples_drake() # List the other examples.
```

# Documentation

The [CRAN page](https://CRAN.R-project.org/package=drake) links to multiple rendered vignettes.

```r
vignette(package = "drake") # List the vignettes.
vignette("drake") # High-level intro.
vignette("quickstart") # Walk through a simple example.
vignette("caution") # Avoid common pitfalls.
```

# Help and troubleshooting

Please refer to [TROUBLESHOOTING.md](https://github.com/wlandau-lilly/drake/blob/master/TROUBLESHOOTING.md) on the [GitHub page](https://github.com/wlandau-lilly/drake) for instructions.

# Background

There is room to improve the conversation and the landscape of reproducibility in the R and Statistics communities. At a more basic level than scientific replicability, literate programming, and version control, reproducibility carries an implicit promise that the alleged results of an analysis really do match the code. Drake helps keep this promise by tracking the relationships among the components of the analysis, a rare and effective approach that also saves time. And with multiple parallel computing options that switch on auto-magically, drake is also a convenient and powerful high-performance computing solution.

The original idea of a time-saving reproducible build system extends back decades to [GNU Make](http://kbroman.org/minimal_make/), which today helps [data scientists](http://blog.kaggle.com/2012/10/15/make-for-data-scientists/) as well as the original user base of complied-language programmers. More recently, [Rich FitzJohn](http://richfitz.github.io/) created [remake](https://github.com/richfitz/remake), a breakthrough reimagining of [Make](http://kbroman.org/minimal_make/) for R and the most important inspiration for drake. Drake is a fresh reinterpretation of some of  [remake](https://github.com/richfitz/remake)'s pioneering fundamental concepts, scaled up for computationally-demanding workflows. 

Thanks also to [Kirill M&uuml;ller](http://krlmlr.github.io/) and [Daniel Falster](http://danielfalster.com/). They contributed code patches and enhancement ideas to my [parallelRemake](https://github.com/wlandau/parallelRemake) and [remakeGenerator](https://github.com/wlandau/remakeGenerator) packages, which I have now subsumed into drake.

In the sphere of reproducibility, drake and [remake](https://github.com/richfitz/remake) are examples of non-literate programming tools (as opposed to literate programming tools such as [knitr](https://CRAN.R-project.org/package=knitr)). Counterparts include [R.cache](https://CRAN.R-project.org/package=R.cache), [archivist](https://CRAN.R-project.org/package=archivist), [trackr](https://github.com/gmbecker/recordr), and [memoise](https://CRAN.R-project.org/package=memoise). See the [reporducible research CRAN task view](https://CRAN.R-project.org/view=ReproducibleResearch) for a more comprehensive list. Drake differentiates itself from these tools with its ability to track the relationships among cached objects and its extensive high-performance computing functionality.
