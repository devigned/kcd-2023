# syntax=docker/dockerfile:1

FROM rust:1.74.0
WORKDIR /app
COPY . /app
RUN rustup target add wasm32-wasi && rustc hello.rs --target wasm32-wasi
RUN curl https://wasmtime.dev/install.sh -sSf | bash
CMD [ "/root/.wasmtime/bin/wasmtime", "hello.wasm" ]