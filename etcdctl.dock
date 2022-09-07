FROM ubuntu:latest
RUN apt-get update -yq
RUN apt-get install -yq tini
RUN apt-get install -yq etcd-client
ENTRYPOINT ["/usr/bin/tini", "--", "/usr/bin/etcdctl"]
CMD ["--help"]
LABEL maintainer="sesrinivasan@purestorage.com"