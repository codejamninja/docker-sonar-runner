FROM openjdk:8-jre-alpine

ENV TAG=stable \
    SONAR_RUNNER_VERSION=2.4

LABEL image=jamrizzi/node-sonar-runner:${TAG} \
      maintainer="Jam Risser <jam@jamrizzi.com>" \
      base=alpine:3.7

RUN apk add --no-cache \
        nodejs \
        tini && \
    npm install -g eslint

RUN cd /tmp && \
    wget http://repo1.maven.org/maven2/org/codehaus/sonar/runner/sonar-runner-dist/${SONAR_RUNNER_VERSION}/sonar-runner-dist-${SONAR_RUNNER_VERSION}.zip && \
    unzip sonar-runner-dist-${SONAR_RUNNER_VERSION}.zip && \
    cp -r /tmp/sonar-runner-${SONAR_RUNNER_VERSION}/* / && \
    cp -r /tmp/sonar-runner-${SONAR_RUNNER_VERSION}/.* / && \
    rm -rf /tmp/*

ENTRYPOINT ["/sbin/tini", "--", "/app/bin/sonar-runner"]
