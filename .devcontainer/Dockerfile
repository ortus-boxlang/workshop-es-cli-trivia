# https://hub.docker.com/r/ortussolutions/boxlang
FROM ortussolutions/boxlang:cli

# Metadata
LABEL maintainer "Ortus Solutions <info@ortussolutions.com>"
LABEL repository "https://github.com/ortus-boxlang/boxlang-docker"

# Utility Packages for our buidling goodness
ENV PACKAGES "ca-certificates openssl openssh-client git"

# Install Common Dependency Binaries
RUN apt-get update && apt-get install --no-install-recommends -y ${PACKAGES} \
    # Cleanup
    && rm -rf /var/lib/{apt,dpkg,cache,log}/ \
    && apt-get clean autoclean \
    && apt-get autoremove -y

# Copy application files to root - Uses .dockerignore to ignore files
COPY ./ ${APP_DIR}/
