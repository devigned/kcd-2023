
.PHONY: run
run:
	rustup target add wasm32-wasi
	rustc hello.rs --target wasm32-wasi
	wasmtime hello.wasm

.PHONY: docker-run
docker-run:
	docker build -t naive-wasm .
	docker run naive-wasm

.PHONY: images
images:
	docker image ls