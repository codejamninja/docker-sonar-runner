FROM kiwicom/sonar-scanner:4.3.0

LABEL image=codejamninja/sonar-scanner:node \
      maintainer="Jam Risser <jam@jamrizzi.com>" \
      base=debian:stretch-slim

USER root

RUN wget -O - https://deb.nodesource.com/setup_12.x | bash && \
  apt-get install -y \
  nodejs && \
  rm -rf /var/lib/apt/lists/*

RUN npm install -g \
  pnpm \
  yarn

ENTRYPOINT []
