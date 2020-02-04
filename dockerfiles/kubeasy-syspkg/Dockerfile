# 1. downloading kernel packages on CentOS7
FROM alpine:3.9 as kernel_centos7

ENV KERNEL_VER=4.19.94

RUN mkdir -p /package/centos7/kernel && \
    cd /package/centos7/kernel && \
    wget http://mirror.centos.org/altarch/7/kernel/x86_64/Packages/kernel-$KERNEL_VER-300.el7.x86_64.rpm && \
    wget http://mirror.centos.org/altarch/7/kernel/x86_64/Packages/kernel-devel-$KERNEL_VER-300.el7.x86_64.rpm && \
    wget http://mirror.centos.org/altarch/7/kernel/x86_64/Packages/kernel-headers-$KERNEL_VER-300.el7.x86_64.rpm && \
    wget http://mirror.centos.org/altarch/7/kernel/x86_64/Packages/kernel-tools-$KERNEL_VER-300.el7.x86_64.rpm && \
    wget http://mirror.centos.org/altarch/7/kernel/x86_64/Packages/kernel-tools-libs-$KERNEL_VER-300.el7.x86_64.rpm && \
    wget http://mirror.centos.org/altarch/7/kernel/x86_64/Packages/kernel-tools-libs-devel-$KERNEL_VER-300.el7.x86_64.rpm && \
    wget http://mirror.centos.org/altarch/7/kernel/x86_64/Packages/kernel-core-$KERNEL_VER-300.el7.x86_64.rpm && \
    wget http://mirror.centos.org/altarch/7/kernel/x86_64/Packages/kernel-cross-headers-$KERNEL_VER-300.el7.x86_64.rpm && \
    wget http://mirror.centos.org/altarch/7/kernel/x86_64/Packages/kernel-modules-$KERNEL_VER-300.el7.x86_64.rpm && \
    wget http://mirror.centos.org/altarch/7/kernel/x86_64/Packages/kernel-modules-extra-$KERNEL_VER-300.el7.x86_64.rpm && \
    wget http://mirror.centos.org/altarch/7/kernel/x86_64/Packages/perf-$KERNEL_VER-300.el7.x86_64.rpm && \
    wget http://mirror.centos.org/altarch/7/kernel/x86_64/Packages/python-perf-$KERNEL_VER-300.el7.x86_64.rpm && \
    tar zcvf /tmp/kernel_centos7.tar.gz *.rpm && \
    rm -rf *
	
# 2.downloading rpm packages on CentOS7
FROM centos:centos7.7.1908 as rpm_centos7

RUN yum install --downloadonly --downloaddir=/root/down \
      bash-completion \
      conntrack-tools \
      ipset \
      ipvsadm \
      libseccomp \
      nfs-utils \
      psmisc \
      rsync \
      socat && \
    cd /root/down && rm -f systemd* && \
    tar zcvf /tmp/basic_centos7.tar.gz *.rpm && \
    rm -rf * && \
    yum install --downloadonly --downloaddir=/root/down chrony && \
    tar zcvf /tmp/chrony_centos7.tar.gz *.rpm && \
    rm -rf * && \
    yum install --downloadonly --downloaddir=/root/down haproxy && \
    tar zcvf /tmp/haproxy_centos7.tar.gz *.rpm && \
    rm -rf * && \
    yum install --downloadonly --downloaddir=/root/down keepalived && \
    tar zcvf /tmp/keepalived_centos7.tar.gz *.rpm && \
    rm -rf *


# 3.storing packages on alpine
FROM alpine:3.9


COPY --from=kernel_centos7 /tmp/*.tar.gz /packages/centos7/
COPY --from=rpm_centos7 /tmp/*.tar.gz /packages/centos7/



CMD [ "sleep", "360000000" ]
