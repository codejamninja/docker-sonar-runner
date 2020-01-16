FROM node:12.14.1-stretch

ENV SONAR_RUNNER_VERSION=4.2.0.1873

LABEL image=codejamninja/sonar-scanner \
      maintainer="Jam Risser <jam@codejam.ninja>" \
      base=ubuntu:stretch

RUN apt-get update && apt-get install -y \
  openjdk-8-jdk \
  && rm -rf /var/lib/apt/lists/*
RUN cd /tmp && \
  wget https://binaries.sonarsource.com/Distribution/sonar-scanner-cli/sonar-scanner-cli-${SONAR_RUNNER_VERSION}-linux.zip && \
  unzip sonar-scanner-cli-${SONAR_RUNNER_VERSION}-linux.zip && \
  mv sonar-scanner-${SONAR_RUNNER_VERSION}-linux /opt/sonar-scanner && \
  ln -s /opt/sonar-scanner/bin/sonar-scanner /usr/local/bin/sonar-scanner

ENTRYPOINT ["/sbin/tini", "--", "/app/bin/sonar-scanner"]
