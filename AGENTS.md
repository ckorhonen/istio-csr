# Repository agent guide

## Repository workflow and completion

`cmd/` is the Go manager entry, `pkg/` the implementation, and `deploy/charts/istio-csr/` the Helm chart. Follow `go.mod` and repository Make tooling. `make test-unit` provisions gotestsum, Go, etcd, kube-apiserver, and kubectl and sets `KUBEBUILDER_ASSETS`; its unit name does not remove local control-plane prerequisites.

Inspect included e2e, CA-rotation, and ECC targets before running them because they create clusters or manipulate certificates. Run relevant isolated checks and identify missing container/Kubernetes prerequisites. Preserve `CONTRIBUTING.md` DCO sign-off. `make release` pushes images and a Helm chart; it is publication, not build validation.

Continue the authorized change through relevant validation and repair of failures it causes; preserve unrelated work. Report checks actually run, commands only inspected, and exact missing prerequisites. Ask only when a material decision, missing authorization, or required input blocks progress; continue independent reversible work. Existing mandatory contribution and validation gates still apply.
