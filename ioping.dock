FROM ubuntu:latest
RUN apt-get update -yq
RUN apt-get install -yq tini
RUN apt-get install -yq ioping
ENTRYPOINT ["/usr/bin/tini", "--", "/usr/bin/ioping"]
CMD ["-D", "/px"]
LABEL maintainer="sesrinivasan@purestorage.com"