# packagerepo
A collection of useful Kubernetes components packaged up as a [Carvel PackageRepo](https://carvel.dev/kapp-controller/docs/latest/packaging/#package-repository)

## Contents
This package repository currently includes:
* [MetalLB](https://github.com/metallb/metallb)
* [Metacontroller](https://github.com/metacontroller/metacontroller)
* [Gitea](https://gitea.io/)
* le-certmanager: A package to set up cert-manager to use a Let's Encrypt Cluster issuer using the DNS solver against AWS Route53, AzureDNS, or GCP DNS
* harbor-project-controller: A metacontroller-based package to create Harbor projects based on custom objects in Kubernetes
* [kube-janitor](https://codeberg.org/hjacobs/kube-janitor)

## Development
### Deploying the repo
First lock the current packages:
```
kbld -f packages/ --imgpkg-lock-output .imgpkg/images.yml
```
Then publish the repo:
```
imgpkg push -b ghcr.io/cdelashmutt-pivotal/package -f .
```