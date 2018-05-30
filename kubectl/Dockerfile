FROM alpine
ENV CONF=/srv/kubectl
ENV VERSION=v1.9.8

RUN apk add --no-cache curl ca-certificates && \
    curl -L https://storage.googleapis.com/kubernetes-release/release/$VERSION/bin/linux/amd64/kubectl -o /usr/local/bin/kubectl && \
    chmod +x /usr/local/bin/kubectl && \
    kubectl version --client

WORKDIR $CONF

#ENTRYPOINT ["kubectl"]
CMD ["kubectl"]