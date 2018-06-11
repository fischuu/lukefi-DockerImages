######################################################################################################  
# Set the starting image
FROM ubuntu:18.04

MAINTAINER Daniel Fischer <daniel.fischer@luke.fi>
  
  ######################################################################################################  
# Install the required system components
RUN apt-get update && apt-get install -y \
curl \
g++ \
gcc \
git \
gstreamer-1.0 \
libcurl4-openssl-dev \
libncurses5-dev \
libncursesw5-dev \
libxslt1-dev \
libgstreamer1.0-dev \
libgstreamer-plugins-base1.0-dev \
libqt5svg5-dev \
make \
openjdk-8-jre \
pigz \
pkg-config \
python \
unzip \
wget \
xcb \
zlib1g-dev \
&& rm -rf /var/lib/apt/lists/*  
  
  ######################################################################################################  
# Install the required Perl components

RUN cpan Bio::Perl \
&& cpan Parallel::ForkManager


# -----------
# samtools 1.3.1
# -----------
  RUN wget -O samtools-1.3.1.tar.bz2 "https://github.com/samtools/samtools/releases/download/1.3.1/samtools-1.3.1.tar.bz2" \
  && tar -xvf samtools-1.3.1.tar.bz2 \
  && cd samtools-1.3.1 && make \
  && make prefix=/bin/samtools-1.3.1 install \
  && rm -r /samtools-1.3.1 \
  && rm /samtools-1.3.1.tar.bz2
  
  
######################################################################################################   
# The the environment variables

  ENV PATH $PATH:/bin/samtools-1.3.1/bin/