# PX_TRIAGE

PX-TRIAGE is a containerized portworx troubleshooting tools. Features will be listed 

1. etcdctl
2. fio
3. ioping
4. iostat
5. mpstat

EXAMPLES:

## ETCDCTL Commands:
docker run --rm -e ETCDCTL_API=3 sens/etcdctl --endpoints "http://x.x.x.x1:9019,http://x.x.x.x2:9019,http://x.x.x.x3:9019" member list -w table
docker run --rm -e ETCDCTL_API=3 sens/etcdctl --endpoints "http://x.x.x.x1:9019,http://x.x.x.x2:9019,http://x.x.x.x3:9019" cluster-health
docker run --rm -e ETCDCTL_API=3 sens/etcdctl --endpoints "http://x.x.x.x1:9019,http://x.x.x.x2:9019,http://x.x.x.x3:9019" check perf
docker run --rm -e ETCDCTL_API=3 sens/etcdctl --endpoints "http://x.x.x.x1:9019,http://x.x.x.x2:9019,http://x.x.x.x3:9019" endpoint health -w table
docker run --rm -e ETCDCTL_API=3 sens/etcdctl --endpoints "http://x.x.x.x1:9019,http://x.x.x.x2:9019,http://x.x.x.x3:9019" defrag
docker run --rm -e ETCDCTL_API=3 sens/etcdctl --endpoints "http://x.x.x.x1:9019,http://x.x.x.x2:9019,http://x.x.x.x3:9019" get --prefix pwx/<cluster-id>/cluster
docker run --rm -e ETCDCTL_API=3 sens/etcdctl --endpoints "http://x.x.x.x1:9019,http://x.x.x.x2:9019,http://x.x.x.x3:9019" get --prefix pwx/<cluster-id>/storage/volumes

## FIO Commands:

docker run --rm -v pxvol:/px sens/fio --blocksize=64k --filename=/mnt/c3 --directory=/mnt/ --ioengine=libaio --readwrite=randrw --size=1G --name=test --end_fsync=1 --gtod_reduce=1 --iodepth=32 --randrepeat=1

docker run --rm -t -v pxvol:/px sens/fio --blocksize=64k -fsync=0 --ioengine=libaio --iodepth=1 --direct=1 --size=100M --rw=write --filename=/px/a --loops=100000


