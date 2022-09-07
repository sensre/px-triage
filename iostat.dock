FROM ubuntu:latest
RUN apt-get update -yq
RUN apt-get install -yq tini
RUN apt-get install -yq sysstat
ENTRYPOINT ["/usr/bin/tini", "--", "/usr/bin/iostat"]
CMD ["-xm","1"]
LABEL maintainer="sesrinivasan@purestorage.com"