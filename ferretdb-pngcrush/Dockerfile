FROM alpine:3.18

RUN apk update && \
    apk add --no-cache pngcrush \
    rm -rf /var/cache/apk/*

WORKDIR /workdir

ENTRYPOINT ["/usr/bin/pngcrush"]
CMD ["-ow", "-brute", "-reduce", "-rem", "allb"]
