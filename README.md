<p align="center">
  <img src="assets/camille.png" alt="Camille, the mascot of Liko" width="240">
</p>

<h1 align="center">cert-manager.liko</h1>

**This repository contains the Cert Manager module for the Liko data language. This module is officially maintained by the Liko team.**

It contains the complete set of Cert Manager schema definitions from the official [Cert Manager repository](https://github.com/cert-manager/cert-manager/releases).

---

## Installation

Initialize a local module with `liko init`, then add `cert-manager.liko` as a dependency.

```bash
liko init
```
```bash
liko add cert-manager
```

```bash
liko install
```

## Usage

The module can now be used from any directory within the current module.

```liko
#CM: import "cert-manager/cert-manager.io/v1"

$: #CM.ClusterIssuer {
    metadata: { name: "letsencrypt" }
    spec: { acme: { server: "https://acme-v02.api.letsencrypt.org/directory" email: "ops@example.org"
                    privateKeySecretRef: { name: "le-key" }
                    solvers: [{ http01: { ingress: { ingressClassName: "nginx" } } }] } }
}
```
