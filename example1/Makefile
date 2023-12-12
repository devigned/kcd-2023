
.PHONY: run
run:
	rustup target add wasm32-wasi
	rustc hello.rs --target wasm32-wasi
	wasmtime hello.wasm