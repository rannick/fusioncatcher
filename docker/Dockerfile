FROM centos:7.6.1810

LABEL Description="This image is used to run FusionCatcher" Version="1.33a"

RUN yum install -y epel-release \
    && yum install -y \
    automake \
    awk \
    which \
    git \
    bzip2 \
    cmake \
    curl \
    gawk \
    gcc \
    gzip  \
    ncurses \
    ncurses-devel \
    make \
    pigz \
    tar \
    unzip \
    wget \
    zlib-devel \
    java-1.8.0-openjdk* \
    tbb-devel \
    glibc-devel \
    python-devel \
    numpy \
    python-biopython \
    python-numpy \
    python-xlrd \
    python-openpyxl \
    java-1.8.9-openjdk*

RUN mkdir -p /apps/fusioncatcher/tools
RUN mkdir -p /apps/fusioncatcher/data

RUN cd /apps/fusioncatcher/tools \
    wget https://github.com/BenLangmead/bowtie/releases/download/v1.2.3/bowtie-1.2.3-linux-x86_64.zip \
    unzip bowtie-1.2.3-linux-x86_64.zip \
    ln -s bowtie-1.2.3-linux-x86_64 bowtie

RUN cd /apps/fusioncatcher/tools \
    wget https://github.com/BenLangmead/bowtie2/releases/download/v2.3.5.1/bowtie2-2.3.5.1-linux-x86_64.zip \
    unzip bowtie2-2.3.5.1-linux-x86_64.zip \
    ln -s bowtie2-2.3.5.1-linux-x86_64 bowtie2

RUN cd /apps/fusioncatcher/tools \
    mkdir blat_v0.35 \
    cd blat_v0.35 \
    wget http://hgdownload.cse.ucsc.edu/admin/exe/linux.x86_64/blat/blat \
    chmod +x blat \
    wget http://hgdownload.cse.ucsc.edu/admin/exe/linux.x86_64/faToTwoBit \
    chmod +x faToTwoBit \
    wget http://hgdownload.cse.ucsc.edu/admin/exe/linux.x86_64/liftOver \
    chmod +x liftOver \
    cd .. \
    ln -s blat_v0.35 blat


RUN cd /apps/fusioncatcher/tools \
    wget http://github.com/ndaniel/seqtk/archive/1.0-r82b.tar.gz -O 1.0-r82b.tar.gz \
    tar zxvf 1.0-r82b.tar.gz \
    cd seqtk-1.0-r82b \
    make \
    cd .. \
    ln -s seqtk-1.0-r82b seqtk

RUN wget https://github.com/ndaniel/fastqtk/archive/v0.27.tar.gz -O v0.27.tar.gz --no-check-certificate \
    tar --overwrite -xvzf v0.27.tar.gz -C . \
    make -C fastqtk-0.27 \
    chmod +x fastqtk-0.27/fastqtk \
    ln -s fastqtk-0.27 fastqtk


RUN cd /apps/fusioncatcher/tools \
    wget http://github.com/alexdobin/STAR/archive/2.7.2b.tar.gz -O 2.7.2b.tar.gz \
    tar zxvf 2.7.2b.tar.gz \
    cd 2.7.2b \
    cd source \
    rm -f STAR \
    cp ../bin/Linux_x86_64_static/STAR . \
    make \
    cd .. \
    ln -s 2.7.2b star \
    cd ../../../




