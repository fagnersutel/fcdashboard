
Funding Circle Dashboard
========================

[FC Dashboard](http://seabbs.co.uk/shiny/fcdashboard) is a shiny application that allows exploratory data analysis of the [Funding Circle](https://www.fundingcircle.com) loanbook. It is not affiliated with Funding Circle, the untransformed loanbook data is not provided.

FC Dashboard can also be used as a personal dashboard to enable you to better understand your investments. To enable this functionality [download your personal loanbook](https://www.fundingcircle.com/investors/historical_loan_parts_summaries.csv?disable_pagination=true) from Funding Circle and upload it using the upload option in the options menu. For the best experiance it is also recommended to upload an up to date copy of the [Funding Circle loanbook](https://www.fundingcircle.com/loanbook) (as the app combines the datasets). Data is stored temporarily during your session only; the app can also be run locally if desired (see instructions below).

Installing the shiny app locally
--------------------------------

### Manual Install

To install and run the shiny app locally on your own computer you will need to first install [R](https://www.r-project.org/), it is also suggested that you install [Rstudio](https://www.rstudio.com/products/rstudio/download/). After downloading the source code from [this repository](https://www.github.com/seabbs/fcdashboard) click on the `fcdashboard.Rprof` file, this will open an Rstudio window. Type the following code into the command line;

``` r
install.packages("shiny")
install.packages("shinydashboard")
install.packages("shinyBS")
install.packages("shinyWidgets")
install.packages("DT")
install.packages("tidyverse")
install.packages("rmarkdown")
install.packages('e1071')
install.packages("caret")
install.packages("ggfortify")
install.packages("plotly")
install.packages("lubridate")
install.packages("wrapr")
install.packages("stringr")
```

Finally save the funding circle loanbook as `loanbook.csv`, and your personal loanbook as `personal_loanbook.csv` in the fcdashboard folder. To run the app open the `ui.R` file and press run, depending on your computer this may take some time. Enjoy exploring the funding circle loanbook!

### Using Docker

[Docker](https://www.docker.com/what-docker) is a container software that seeks to eliminate "works on my machine" issues. For installation and set up instructions see [here](https://www.docker.com/community-edition).

This docker container is based on the [shiny](https://hub.docker.com/r/rocker/shiny/) docker image, see [here](https://github.com/rocker-org/shiny) for instructions on use. To run the docker image run the following in a bash shell:

``` bash
docker pull seabbs/fcdashboard
docker run --rm -p 3838:3838 seabbs/fcdashboard
```

The shiny server can be found on port `:3838` at your local machines ip (or localhost on windows), fcdashboard can be found at `your-ip:3838/fcdashboard`.
