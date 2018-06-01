FROM alpine
ENV CONF=/srv/kubectl
ENV KCTL_VERSION=v1.9.8
ENV HELM_VERSION=v2.9.1

RUN apk add --no-cache curl ca-certificates git && \
    curl -L https://storage.googleapis.com/kubernetes-release/release/$KCTL_VERSION/bin/linux/amd64/kubectl -o /usr/local/bin/kubectl && \
    chmod +x /usr/local/bin/kubectl && \
    kubectl version --client

ARG FILENAME=helm-${HELM_VERSION}-linux-amd64.tar.gz

WORKDIR /

RUN apk add --update -t deps curl tar gzip
RUN curl -L http://storage.googleapis.com/kubernetes-helm/${FILENAME} | tar zxv -C /tmp

RUN mv /tmp/linux-amd64/helm /bin/helm

WORKDIR $CONF

CMD ["kubectl"]
