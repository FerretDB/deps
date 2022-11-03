FROM node:18.12.0-alpine3.16

WORKDIR /workdir/ferretdb-textlint
COPY *.json .
RUN npm ci

# https://github.com/opencontainers/image-spec/blob/main/annotations.md
LABEL org.opencontainers.image.source="https://github.com/FerretDB/deps"

ENTRYPOINT ["/workdir/ferretdb-textlint/node_modules/.bin/textlint"]
CMD ["-h"]
