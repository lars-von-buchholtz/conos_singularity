BootStrap: docker
From: rocker/tidyverse:4.0.1

%labels
    authors="Viktor Petukhov <viktor.s.petuhov@ya.ru>, Evan Biederstedt <evan.biederstedt@gmail.com>" \
    version.image="1.4.0" \
    version.pagoda2="1.4.0" \
    description="tidyverse image R 4.0.1 to run pagoda2 with Rstudio"

%post

apt-get update --yes && apt-get install --no-install-recommends --yes \
  build-essential \
  cmake \
  git \
  less \
  libcurl4-openssl-dev \
  libssl-dev \
  libgsl0-dev \
  libeigen3-dev \
  libssl-dev \
  libcurl4-openssl-dev \
  libssl-dev \
  libcairo2-dev \
  libxt-dev \
  libgtk2.0-dev \
  libcairo2-dev \
  xvfb  \
  xauth \
  xfonts-base \
  libz-dev \
  libhdf5-dev


R -e 'chooseCRANmirror(ind=52); install.packages("BiocManager")'
R -e 'BiocManager::install(c("AnnotationDbi", "BiocGenerics", "GO.db", "pcaMethods", "org.Dr.eg.db", "org.Hs.eg.db", "org.Mm.eg.db", "scde", "BiocParallel"))'

R -e "install.packages('Seurat',dependencies=TRUE, repos='http://cran.rstudio.com/')"


R -e "install.packages('p2data',dependencies=TRUE, repos='https://kharchenkolab.github.io/drat/', type='source')"

R -e "install.packages('pagoda2',dependencies=TRUE, repos='http://cran.rstudio.com/')"

R -e "install.packages('conosPanel',dependencies=TRUE, repos='https://kharchenkolab.github.io/drat/', type='source')"

R -e 'devtools::install_github("kharchenkolab/conos")'

###
### destination for NIH HPC bind mounts
###

mkdir /gpfs /spin1 /gs2 /gs3 /gs4 /gs5 /gs6 /gs7 /gs8 /data /scratch /fdb /lscratch
