# kube-oidc

This chart deploys:
* [dex](https://github.com/dexidp/dex): identity provider supporting multiple connectors (SAML, LDAP...)
* [loginapp](https://github.com/fydrah/loginapp): web application for Kubernetes cli configuration with OIDC
* [keycloak proxy](https://github.com/keycloak/keycloak-gatekeeper): OpenID / Keycloak proxy service (used for OIDC dashboard auth)

## Install

* From chart repository:

```
helm repo add fydrahcharts https://charts.fhardy.fr
helm repo update
```

Override [default configuration](./values.yaml) with an `override.yaml` file.

```
helm install fydrahcharts/kube-oidc -f override.yaml
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

## Examples

* [SAML configuration](./examples/SAML.md)
* [Cross client configuration for k8s](./examples/cross-client.md)
