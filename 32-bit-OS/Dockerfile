FROM 32bit/ubuntu:14.04

MAINTAINER Asif Sardar <engr.asif.sardar@gmail.com>

ENV DEBIAN_FRONTEND noninteractive

RUN echo "deb http://ppa.launchpad.net/terry.guo/gcc-arm-embedded/ubuntu trusty main" > /etc/apt/sources.list.d/gcc-arm-embedded.list
RUN apt-key adv --keyserver keyserver.ubuntu.com --recv-key FE324A81C208C89497EFC6246D1D8367A3421AFB

RUN apt-get update 
RUN apt-get -y dist-upgrade

RUN apt-get -y install \
	make \
	gcc \
	g++ \
	git \
	subversion \
	wget \
	curl \
	nano \
	p7zip \
	unzip \
	python2.7 \
	python2.7-dev \
	python-setuptools \
	bridge-utils \
	libpcre3 \
	pcregrep

# Cortex-M development
RUN apt-get -y install \
    gcc-arm-none-eabi \
    libnewlib-dev

#ADD https://launchpad.net/gcc-arm-embedded/4.9/4.9-2014-q4-major/+download/gcc-arm-none-eabi-4_9-2014q4-20141203-linux.tar.bz2 /home/Downloads/
#WORKDIR /home/Downloads/
#RUN tar xvjf gcc-arm-none-eabi-4_9-2014q4-20141203-linux.tar.bz2
#ENV PATH /home/Downloads/gcc-arm-none-eabi-4_9-2014q4/bin:$PATH

WORKDIR /home/
RUN git clone https://github.com/Ell-i/stm32flash.git
RUN export PATH=${PATH}:/home/stm32flash/

RUN easy_install -Z robotframework
RUN easy_install -Z docutils

#RUN git clone https://github.com/asifsardar26/Runtime.git /home/Runtime
#RUN git --git-dir /home/Runtime/.git --work-tree /home/Runtime checkout feature-encX24J600-wip

#RUN git clone https://github.com/asifsardar26/ELL-i-PyBot-Tests /home/Runtime/robot_tests/

#RUN git clone git://github.com/RIOT-OS/RIOT /home/RIOT

#VOLUME ["/home"]

WORKDIR /home

CMD ["/bin/bash"]
