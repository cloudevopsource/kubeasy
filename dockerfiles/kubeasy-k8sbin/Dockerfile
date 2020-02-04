# Download kubernetes binaries to container
# @date:    2019/12/15
# @author:  orasun@vip.qq.com
# @repo:    https://https://github.com/cloudevopsource/kubeasy/edit/master/dockerfiles/kubeasy-k8s-bin

FROM alpine:3.9

ENV K8S_VER=v1.16.4

RUN wget https://dl.k8s.io/$K8S_VER/kubernetes-server-linux-amd64.tar.gz && \
    tar zxf kubernetes-server-linux-amd64.tar.gz && \
    mkdir -p /packages/k8s && cd kubernetes/server/bin && \
    mv kube-apiserver kube-controller-manager kube-scheduler /packages/k8s && \
    mv kubelet kube-proxy kubectl /packages/k8s && \
    cd / && rm -rf kubernetes*

CMD [ "sleep", "360000000" ]
