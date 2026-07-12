FROM ubuntu:24.04

RUN apt-get update
RUN apt-get install -y curl git make sudo
RUN curl -O https://practicerom.com/public/packages/debian/dists/stable/practicerom-repository_latest_$(dpkg --print-architecture).deb
RUN dpkg -i practicerom-repository_latest_$(dpkg --print-architecture).deb
RUN rm practicerom-repository_latest_$(dpkg --print-architecture).deb
RUN apt-get update
RUN apt-get install -y practicerom-dev

RUN groupadd -g 1001 practicerom-dev
RUN useradd -u 1001 -g 1001 -m -d /home/practicerom-dev practicerom-dev
RUN echo 'practicerom-dev ALL=(ALL:ALL) NOPASSWD: ALL' >/etc/sudoers.d/practicerom-dev

USER practicerom-dev
WORKDIR /home/practicerom-dev
