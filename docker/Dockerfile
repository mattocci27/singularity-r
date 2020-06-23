FROM ubuntu:focal

ARG R_VERSION=4.0.2
ENV DEBIAN_FRONTEND=noninteractive

RUN  sed -i.bak -e "s%http://archive.ubuntu.com/%http://mirrors.tuna.tsinghua.edu.cn/%g" /etc/apt/sources.list \
  && sed -i.bak -e "s%http://security.ubuntu.com/%http://mirrors.tuna.tsinghua.edu.cn/%g" /etc/apt/sources.list \
  && apt-get update \
  && apt-get install -y --no-install-recommends \
    locales \
    gnupg \
  # Configure default locale
  && echo "en_US.UTF-8 UTF-8" >> /etc/locale.gen \
  && locale-gen en_US.utf8 \
  && /usr/sbin/update-locale LANG=en_US.UTF-8 \
  && export LC_ALL=en_US.UTF-8 \
  && export LANG=en_US.UTF-8 \
  # Install R
  && echo "deb http://cran.r-project.org/bin/linux/ubuntu focal-cran40/" > /etc/apt/sources.list.d/r.list \
  && apt-key adv --keyserver keyserver.ubuntu.com --recv-keys E298A3A825C0D65DFD57CBB651716619E084DAB9 \
  && apt-get update \
  && DEBIAN_FRONTEND=noninteractive apt-get install -y --no-install-recommends \
    r-base=${R_VERSION}* \
    r-base-core=${R_VERSION}* \
    r-base-dev=${R_VERSION}* \
    r-recommended=${R_VERSION}* \
    r-base-html=${R_VERSION}* \
    r-doc-html=${R_VERSION}* \
    libcurl4-openssl-dev \
    libssl-dev \
    libxml2-dev \
    libcairo2-dev \
    libxt-dev \
    libopenblas-openmp-dev \
  && echo "options(repos = c(CRAN = 'https://cran.rstudio.com/'), download.file.method = 'libcurl')" >> /usr/lib/R/etc/Rprofile.site \
  && mkdir -p /library \
  && echo "R_LIBS_SITE=/library:\${R_LIBS_SITE}" >> /usr/lib/R/etc/Renviron.site \
  && rm -rf /var/lib/apt/lists/*
