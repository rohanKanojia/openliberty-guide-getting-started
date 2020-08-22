FROM openliberty/open-liberty:kernel-java8-openj9-ubi

ARG VERSION=1.0
ARG REVISION=SNAPSHOT

LABEL \
  org.opencontainers.image.authors="Your Name" \
  org.opencontainers.image.vendor="IBM" \
  org.opencontainers.image.url="local" \
  org.opencontainers.image.source="https://github.com/OpenLiberty/guide-getting-started" \
  org.opencontainers.image.version="$VERSION" \
  org.opencontainers.image.revision="$REVISION" \
  vendor="Open Liberty" \
  name="system" \
  version="$VERSION-$REVISION" \
  summary="The system microservice from the Getting Started guide" \
  description="This image contains the system microservice running with the Open Liberty runtime."

# Eclipse JKube's default assembly name, files are packaged under this folder:
ARG JKUBE_DEFAULT_ASSEMBLY=maven
COPY --chown=1001:0 $JKUBE_DEFAULT_ASSEMBLY/src/main/liberty/config/ /config/
COPY --chown=1001:0 $JKUBE_DEFAULT_ASSEMBLY/target/*.war /config/apps/

# Expose Ports
EXPOSE 9080
EXPOSE 9443

RUN configure.sh
