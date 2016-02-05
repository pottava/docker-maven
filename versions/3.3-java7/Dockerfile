# Maven v3.3
# docker run --rm pottava/maven:3.3-java7 mvn -v

FROM pottava/java:7

ENV MAVEN_VERSION=3.3.9 \
    MAVEN_HOME=/opt/maven

RUN set -ex \
      && apk --no-cache add --virtual build-dependencies wget \
      && cd /opt \
      && wget --quiet http://archive.apache.org/dist/maven/maven-3/$MAVEN_VERSION/binaries/apache-maven-$MAVEN_VERSION-bin.tar.gz -O - | tar xzf - \
      && mv /opt/apache-maven-$MAVEN_VERSION /opt/maven \
      && ln -s /opt/maven/bin/mvn /usr/bin/mvn \
      && apk del --purge build-dependencies
