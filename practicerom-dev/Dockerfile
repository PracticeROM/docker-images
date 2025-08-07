FROM ubuntu:24.04

RUN apt-get update
RUN apt-get install -y curl git make sudo
RUN sh -c "$(curl -fsSL https://raw.githubusercontent.com/PracticeROM/packages/HEAD/scripts/install-debian_amd64.sh)"
RUN apt-get install -y practicerom-dev

RUN groupadd -g 1001 practicerom-dev
RUN useradd -u 1001 -g 1001 -m -d /home/practicerom-dev practicerom-dev
RUN echo 'practicerom-dev ALL=(ALL:ALL) NOPASSWD: ALL' >/etc/sudoers.d/practicerom-dev

USER practicerom-dev
WORKDIR /home/practicerom-dev
