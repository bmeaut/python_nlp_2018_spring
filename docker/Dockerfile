FROM ubuntu:latest
MAINTAINER Judit Acs

WORKDIR /nlp

RUN apt-get update \
        && apt-get install -y python3-pip python3-dev \
        && cd /usr/local/bin \
        && ln -s /usr/bin/python3 python \
        && pip3 install --upgrade pip
RUN apt-get install -y wget git unzip less iputils-ping
RUN pip3 install numpy scipy nltk jupyter
RUN python -c 'import nltk;nltk.download("wordnet")'
RUN mkdir -p /nlp/hfst && cd /nlp/hfst && wget https://apertium.projectjj.com/apt/install-nightly.sh && bash install-nightly.sh

RUN cd /nlp/hfst && wget http://apertium.projectjj.com/apt/nightly/pool/main/h/hfst/libhfst51_3.14.0+g3229~80a2bcd1-1~xenial1_amd64.deb && dpkg -i libhfst51_3.14.0+g3229~80a2bcd1-1~xenial1_amd64.deb
RUN cd /nlp/hfst && wget http://apertium.projectjj.com/apt/nightly/pool/main/h/hfst/hfst_3.14.0+g3229~80a2bcd1-1~xenial1_amd64.deb && dpkg -i hfst_3.14.0+g3229~80a2bcd1-1~xenial1_amd64.deb

RUN cd /nlp/hfst && wget http://sandbox.mokk.bme.hu/~judit/resources/hu.hfstol

RUN cd /nlp && git clone https://github.com/bmeaut/python_nlp_2018_spring.git

RUN apt-get install -y foma-bin

EXPOSE 8088
