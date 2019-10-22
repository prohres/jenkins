###/
# Dockefile to build Docker Image of setup systemd running on Centos
#
# Solovii Serhii 23/03/2019
###/

FROM centos:centos7

RUN yum install -y net-tools vim make

ENV container=docker  
 
COPY container.target /etc/systemd/system/container.target
 
RUN ln -sf /etc/systemd/system/container.target /etc/systemd/system/default.target

ENTRYPOINT ["/sbin/init"]
 
CMD ["--log-level=info"]
 
STOPSIGNAL SIGRTMIN+3

RUN --mount type=bind,source=/sys/fs/cgroup,target=/sys/fs/cgroup \
    --mount type=bind,source=/sys/fs/fuse,target=/sys/fs/fuse \
    --mount type=tmpfs,destination=/run \
    --mount type=tmpfs,destination=/run/lock