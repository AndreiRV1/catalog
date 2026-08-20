FROM rust:1.75.0-bookworm AS build

WORKDIR /src

COPY ./helloworld.rs /src/helloworld.rs

RUN set -xe; \
    rustc -o /helloworld /src/helloworld.rs

FROM gcr.io/distroless/cc-debian12

COPY --from=build /helloworld /helloworld

