FROM ubuntu:23.04

RUN apt update && apt upgrade -y
RUN apt install -y file libicu-dev pkg-config libncurses5 binutils libelf1

RUN mkdir /tmp/gtm-distro
RUN useradd -m gtm
ADD gtm_V70005_linux_x8664_pro.tar.gz /tmp/gtm-distro
ADD gtm-install-options /tmp
RUN cd /tmp/gtm-distro/ && \
    ./configure < /tmp/gtm-install-options && \
    rm -r /tmp/* && \
    echo ". /opt/fis-gtm/gtmprofile" > /home/gtm/.bashrc

USER gtm
ENTRYPOINT [ "bash" ]
