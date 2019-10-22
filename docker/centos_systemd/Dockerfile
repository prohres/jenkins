###/
# Dockefile to build Docker Image of setup systemd running on Centos
#
# Solovii Serhii 23/03/2019
###/

FROM centos:centos7

RUN yum install -y net-tools vim make tree

ENV container=docker  
 
COPY container.target /etc/systemd/system/container.target
 
RUN ln -sf /etc/systemd/system/container.target /etc/systemd/system/default.target

ENTRYPOINT ["/sbin/init"]
 
CMD ["--log-level=info"]
 
STOPSIGNAL SIGRTMIN+3
