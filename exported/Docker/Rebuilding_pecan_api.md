

In docker directory

`cd /mnt/shared/projects/joint/202012_RETINA/pecan/docker/`

check to make sure it’s pecan

`docker compose down`

in the pecan api directory

`cd apps/api`

`docker build -t pecan/api:develop .`

then back in docker directory

`docker compose up -d`

docker exec -it [retina.hutton.ac.uk](http://retina.hutton.ac.uk/) bash

```jsx
#0 2882.1 ERROR: dependency 'pkgdown' is not available for package 'devtools'
#0 2882.1 * removing '/usr/lib64/R/library/devtools'
#0 2882.1 ERROR: dependencies 'leafem', 'leafpop', 'sf' are not available for package 'mapview'
#0 2882.1 * removing '/usr/lib64/R/library/mapview'
#0 2882.1
#0 2882.1 The downloaded source packages are in
#0 2882.1       '/tmp/RtmpVk4Erv/downloaded_packages'
#0 2882.1 Updating HTML index of packages in '.Library'
#0 2882.1 Making 'packages.html' ... done
#0 2882.1 There were 22 warnings (use warnings() to see them)
#0 2882.1 Error in loadNamespace(x) : there is no package called 'devtools'
#0 2882.1 Calls: loadNamespace -> withRestarts -> withOneRestart -> doWithOneRestart
#0 2882.1 Execution halted
------
Dockerfile:22
--------------------
  21 |
  22 | >>> RUN Rscript -e "install.packages(c('DBI', 'devtools', 'dbplyr', 'dplyr', 'ggplot2', 'htmlwidgets', 'magrittr', 'ncdf4', 'plotly',  'rgdal', 'rgeos', 'raster', 'RPostgres', 'tidyr', 'xml2'), dependencies = TRUE, repos = '<http://cran.rstudio.com>')" && \\
  23 | >>>     Rscript -e "devtools::install_github('pecanproject/rpecanapi')"
  24 |
--------------------
ERROR: failed to solve: process "/bin/sh -c Rscript -e \\"install.packages(c('DBI', 'devtools', 'dbplyr', 'dplyr', 'ggplot2', 'htmlwidgets', 'magrittr', 'ncdf4', 'plotly',  'rgdal', 'rgeos', 'raster', 'RPostgres', 'tidyr', 'xml2'), dependencies = TRUE, repos = '<http://cran.rstudio.com>')\\" &&     Rscript -e \\"devtools::install_github('pecanproject/rpecanapi')\\"" did not complete successfully: exit code: 1
```