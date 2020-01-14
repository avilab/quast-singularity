Bootstrap: docker
From: ubuntu:18.04

%labels
  Maintainer tpall

%post
apt-get update && DEBIAN_FRONTEND="noninteractive" apt-get -y install tzdata \
  && apt-get -y install \
  wget \
  build-essential \
  git \
  zlib1g-dev \
  pkg-config \
  libfreetype6-dev \
  libpng-dev \
  python-setuptools \
  python-matplotlib

git clone https://github.com/ablab/quast.git \
  && cd quast \
  && ./setup.py install_full

## Clean up
apt-get clean \
  && rm -rf /var/lib/apt/lists/ 

%environment
  export PATH=/usr/local/bin:$PATH
  export LC_ALL=C
