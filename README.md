# kube-oidc

This chart deploys:
* [dex](https://github.com/dexidp/dex): identity provider supporting multiple connectors (SAML, LDAP...)
* [loginapp](https://github.com/fydrah/loginapp): web application for Kubernetes cli configuration with OIDC
* [keycloak proxy](https://github.com/keycloak/keycloak-gatekeeper): OpenID / Keycloak proxy service (used for OIDC dashboard auth)

## Install

* From chart repository:

```
helm repo add fhardy-stable https://registry.fhardy.fr/chartrepo/stable
helm repo update
```

Override [default configuration](./values.yaml) with an `override.yaml` file.

```
helm install fhardy-stable/kube-oidc -f override.yaml
```

* From GitHub:

```
git clone https://github.com/ObjectifLibre/kube-oidc
```

Override [default configuration](./values.yaml) with an `override.yaml` file.

```
cd kube-oidc/
helm install . -f override.yaml
```

## Configure

See [values.yaml](./values.yaml).

## Changes on kuberentes

See [kube-apiserver oidc](https://kubernetes.io/docs/reference/access-authn-authz/authentication/#openid-connect-tokens)

## Examples

* [SAML configuration](./examples/SAML.md)
* [Cross client configuration for k8s](./examples/cross-client.md)
