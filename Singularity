Bootstrap: docker
From: ubuntu:latest

%labels
  Maintainer tpall



%post
echo 'export DEBIAN_FRONTEND=noninteractive' >>$SINGULARITY_ENVIRONMENT
apt-get update && apt-get -y install \
  wget \
  build-essential \
  zlib1g-dev \
  pkg-config \
  libfreetype6-dev \
  libpng-dev \
  tzdata \
  python-setuptools \
  python-matplotlib

wget https://downloads.sourceforge.net/project/quast/quast-5.0.2.tar.gz \
  && tar -xzf quast-5.0.2.tar.gz \
  && cd quast-5.0.2 \
  && ./setup.py install_full

## Clean up
apt-get clean \
  && rm -rf /var/lib/apt/lists/ 

cd / \
  && rm -rf quast-5.0.2 \
  && rm quast-5.0.2.tar.gz

%environment
  export PATH=/usr/local/bin:$PATH
  export LC_ALL=C
