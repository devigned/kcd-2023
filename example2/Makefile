
.PHONY: cluster
cluster:
	docker build -f Dockerfile.oci . -t kind-oci
	kind create cluster --image kind-oci --config kind-config.yaml -n spin-oci
	kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/kind/deploy.yaml

.PHONY: apply
apply: push
	kubectl apply -f deployment.yaml

.PHONY: serve
serve:
	spin build -f ./future/spin.toml --up

.PHONY: push
push:
	spin registry push -f ./future/spin.toml devigned/spin-test:latest

.PHONY: clean
clean:
	kind delete cluster -n spin-oci
