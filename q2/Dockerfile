FROM sonarsource/sonar-scanner-cli:4.3

LABEL image=codejamninja/sonar-scanner:q2 \
      maintainer="Jam Risser <jam@jamrizzi.com>" \
      base=debian:stretch-slim

USER root

RUN wget -O - https://deb.nodesource.com/setup_12.x | bash && \
  apt-get install -y \
  make \
  nodejs \
  python3 \
  python3-pip && \
  rm -rf /var/lib/apt/lists/*

RUN pip3 install virtualenv

RUN npm install -g \
  pnpm \
  yarn

ENTRYPOINT []
