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
# trimmomatic v0.36
# -----------  
  RUN wget  -O Trimmomatic-0.36.zip  http://www.usadellab.org/cms/uploads/supplementary/Trimmomatic/Trimmomatic-0.36.zip \
  && unzip Trimmomatic-0.36.zip \
  && cp /Trimmomatic-0.36/trimmomatic-0.36.jar /bin/ \
  && rm -r Trimmomatic-0.36/
  
  
  