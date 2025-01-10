FROM node:22.13.0-alpine

WORKDIR /deps
COPY *.json .
RUN npm ci

WORKDIR /workdir
ENTRYPOINT ["/deps/node_modules/.bin/textlint"]
CMD ["-h"]

# https://github.com/opencontainers/image-spec/blob/main/annotations.md
LABEL org.opencontainers.image.source="https://github.com/FerretDB/deps"
