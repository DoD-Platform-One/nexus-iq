# Sonatype Nexus IQ

Monitoring and notifications of open source vulnerabilities

This chart was sourced from
[Sonatype's Helm Charts.](https://github.com/sonatype/helm3-charts) with
minimal changes.

## Prerequisites

- Kubernetes Cluster deployed
- Kubernetes config installed in ~/.kube/config
- Helm installed
- Keycloak (Optional - SSO)
- Sonatype NXIQ License. Required for SAML integration

## Iron Bank

You can `pull` the Iron Bank image [here](https://registry1.dso.mil/harbor/projects/3/repositories/sonatype%2Fnexus-iq-server%2Fnexus-iq-server) and view the container approval [here](https://ironbank.dso.mil/repomap/sonatype/nexus-iq-server).

## Helm

Please reference complete list of providable variables
[here](https://github.com/sonatype/helm3-charts/tree/master/charts/nexus-iq#chart-configuration-options)

```bash
git clone https://repo1.dso.mil/platform-one/big-bang/apps/third-party/nexus-iq.git
helm install nexus-iq chart
```

## BigBang Additions, Comments, and Important Information
### SAML/SSO Integration
BigBang requires/prefers SAML/SSO integration out of the box, unfortunately, the upstream Helm chart did not have a
solution at the drafting of this integration. To achieve our goal, we added a Kubernetes job that handles the SAML/SSO
integration. To enable this functionality, ensure `sso.enabled` is set to `true`; you will additionally require a
Keycloak instance, the IDP metadata file, along with the other parameters you may define in the `values.yaml`. Our
implementation closely followed [Sonatype's API](https://help.sonatype.com/iqserver/automating/rest-apis/saml-rest-api---v2#SAMLRESTAPI-v2-ConfigureSAMLIntegration).

### Default Admin Password
Sonatype's API prevents the changing of a user's password via API. It was deemed more feature-breaking to introduce a
viable workaround. Please change your admin password immediately.

Sonatype is tracking this issue with an internal ticket.

### License
We expect you to secure your license; the license will be provided as a binary. Encode the binary file as a base64
encoded string, secure with sops, and place in `.Values.addons.nexusRepositoryManager.license_key`. The `_helpers.tpl`
will create a named template and generate the appropriate secret within the namespace. The chart will reference the
license via a secret volumeMount to ensure the application starts licensed.
