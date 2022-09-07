FROM ubuntu:latest
RUN apt-get update -yq
RUN apt-get install -yq fio tini
ENTRYPOINT ["/usr/bin/tini", "--", "/usr/bin/fio"]
CMD ["--name=px", "--blocksize=64k", "--gtod_reduce=1", "--fsync=0", "--end_fsync=1", "--ioengine=libaio", "--iodepth=256", "--direct=1", "--size=10G", "--rw=write", "--filename=/px/a" ]
LABEL maintainer="sesrinivasan@purestorage.com"