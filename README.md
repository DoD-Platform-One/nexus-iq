# nexus-iq-server

![Version: 194.0.0-bb.0](https://img.shields.io/badge/Version-188.0.0--bb.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 1.194.0](https://img.shields.io/badge/AppVersion-1.194.0-informational?style=flat-square)

## Upstream References
* <https://www.sonatype.com/product-nexus-lifecycle>

## Learn More
* [Application Overview](docs/overview.md)
* [Other Documentation](docs/)

## Pre-Requisites

* Kubernetes Cluster deployed
* Kubernetes config installed in `~/.kube/config`
* Helm installed

Install Helm

https://helm.sh/docs/intro/install/

## Deployment

* Clone down the repository
* cd into directory
```bash
helm install nexus-iq-server chart/
```

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| domain | string | `"bigbang.dev"` |  |
| hostname | string | `"nexus-iq-server"` |  |
| istio.enabled | bool | `false` |  |
| istio.iqserver.gateways[0] | string | `"istio-system/public"` |  |
| license_key | string | `""` |  |
| admin.username | string | `"admin"` |  |
| admin.password | string | `"admin123"` |  |
| certificates.image.repository | string | `"registry1.dso.mil/ironbank/sonatype/nexus-iq-server/nexus-iq-server"` |  |
| certificates.image.tag | string | `"1.194.0-01"` |  |
| certificates.image.pullPolicy | string | `"IfNotPresent"` |  |
| certificates.truststore.password | string | `"changeit"` |  |
| certificates.customCAs[0].secret | string | `"ca-certs-dod-trust-anchors"` |  |
| certificates.customCAs[1].secret | string | `"ca-certs-dod-intermediate-dod-email-ca"` |  |
| certificates.customCAs[2].secret | string | `"ca-certs-dod-intermediate-dod-id-ca"` |  |
| certificates.customCAs[3].secret | string | `"ca-certs-dod-intermediate-dod-id-sw-ca"` |  |
| certificates.customCAs[4].secret | string | `"ca-certs-dod-intermediate-dod-sw-ca"` |  |
| certificates.customCAs[5].secret | string | `"ca-certs-eca-sha-1"` |  |
| certificates.customCAs[6].secret | string | `"ca-certs-eca-sha-256"` |  |
| certificates.customCAs[7].secret | string | `"ca-certs-ado-sha-256-cc-chain"` |  |
| certificates.customCAs[8].secret | string | `"ca-certs-ado-sha-256-dt-chain"` |  |
| certificates.customCAs[9].secret | string | `"ca-certs-boeing-sha-1"` |  |
| certificates.customCAs[10].secret | string | `"ca-certs-carillon-federal-services"` |  |
| certificates.customCAs[11].secret | string | `"ca-certs-department-of-state-trust-chain-1"` |  |
| certificates.customCAs[12].secret | string | `"ca-certs-department-of-state-trust-chain-2"` |  |
| certificates.customCAs[13].secret | string | `"ca-certs-entrust-nfi-trust-chain-1"` |  |
| certificates.customCAs[14].secret | string | `"ca-certs-entrust-nfi-trust-chain-2"` |  |
| certificates.customCAs[15].secret | string | `"ca-certs-entrust-ssp"` |  |
| certificates.customCAs[16].secret | string | `"ca-certs-exostar-llc"` |  |
| certificates.customCAs[17].secret | string | `"ca-certs-identrust-nfi"` |  |
| certificates.customCAs[18].secret | string | `"ca-certs-lockheed-martin-sha-256"` |  |
| certificates.customCAs[19].secret | string | `"ca-certs-nl-mod"` |  |
| certificates.customCAs[20].secret | string | `"ca-certs-northrop-grumman-sha-256"` |  |
| certificates.customCAs[21].secret | string | `"ca-certs-orc-nfi"` |  |
| certificates.customCAs[22].secret | string | `"ca-certs-orc-ssp"` |  |
| certificates.customCAs[23].secret | string | `"ca-certs-raytheon-sha-1"` |  |
| certificates.customCAs[24].secret | string | `"ca-certs-raytheon-sha-256"` |  |
| certificates.customCAs[25].secret | string | `"ca-certs-symantec-nfi-trust-chain-1"` |  |
| certificates.customCAs[26].secret | string | `"ca-certs-symantec-nfi-trust-chain-2"` |  |
| certificates.customCAs[27].secret | string | `"ca-certs-symantec-ssp-trust-chain-1"` |  |
| certificates.customCAs[28].secret | string | `"ca-certs-symantec-ssp-trust-chain-2"` |  |
| certificates.customCAs[29].secret | string | `"ca-certs-treasury-ssp-trust-chain-1"` |  |
| certificates.customCAs[30].secret | string | `"ca-certs-treasury-ssp-trust-chain-2"` |  |
| certificates.customCAs[31].secret | string | `"ca-certs-verizon-business-nfi"` |  |
| certificates.customCAs[32].secret | string | `"ca-certs-verizon-business-ssp-trust-chain-1"` |  |
| certificates.customCAs[33].secret | string | `"ca-certs-verizon-business-ssp-trust-chain-2"` |  |
| mail.enabled | bool | `false` |  |
| mail.mailConfiguration | object | `{}` |  |
| sso.enabled | bool | `false` |  |
| sso.idp_metadata | string | `""` |  |
| sso.samlConfiguration | object | `{}` |  |
| statefulset.enabled | bool | `false` |  |
| replicaCount | int | `1` |  |
| image.repository | string | `"registry1.dso.mil/ironbank/sonatype/nexus-iq-server/nexus-iq-server"` |  |
| image.tag | string | `"1.194.0-01"` |  |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| job_image.repository | string | `"registry1.dso.mil/ironbank/redhat/ubi/ubi9-minimal"` |  |
| job_image.tag | float | `9.4` |  |
| job_image.pullPolicy | string | `"IfNotPresent"` |  |
| iq.name | string | `"nxiq"` |  |
| iq.hostname | string | `"iq-server.demo"` |  |
| iq.applicationPort | int | `8070` |  |
| iq.adminPort | int | `8071` |  |
| iq.memory | string | `"1Gi"` |  |
| iq.licenseSecret | string | `""` |  |
| iq.extraLabels | string | `nil` |  |
| iq.secretName | string | `nil` |  |
| iq.secretMountName | string | `nil` |  |
| iq.env[0].name | string | `"JAVA_OPTS"` |  |
| iq.env[0].value | string | `"-Djava.util.prefs.userRoot=$${SONATYPE_WORK}/javaprefs"` |  |
| iq.livenessProbe.initialDelaySeconds | int | `10` |  |
| iq.livenessProbe.periodSeconds | int | `10` |  |
| iq.livenessProbe.failureThreshold | int | `3` |  |
| iq.livenessProbe.timeoutSeconds | int | `2` |  |
| iq.livenessProbe.successThreshold | int | `1` |  |
| iq.readinessProbe.initialDelaySeconds | int | `30` |  |
| iq.readinessProbe.periodSeconds | int | `30` |  |
| iq.readinessProbe.failureThreshold | int | `10` |  |
| iq.readinessProbe.timeoutSeconds | int | `2` |  |
| iq.readinessProbe.successThreshold | int | `1` |  |
| fixOwner.enabled | bool | `false` |  |
| deploymentStrategy | string | `"Recreate"` |  |
| imagePullSecrets | list | `[]` |  |
| nameOverride | string | `""` |  |
| fullnameOverride | string | `"nexus-iq"` |  |
| serviceAccount.create | bool | `true` |  |
| serviceAccount.annotations | object | `{}` |  |
| serviceAccount.name | string | `nil` |  |
| podAnnotations | string | `nil` |  |
| podSecurityContext | object | `{}` |  |
| securityContext | object | `{}` |  |
| service.type | string | `"ClusterIP"` |  |
| service.port | int | `80` |  |
| ingress.enabled | bool | `false` |  |
| ingress.annotations."kubernetes.io/ingress.class" | string | `"nginx"` |  |
| ingress.hostUI | string | `"iq-server.demo"` |  |
| ingress.hostUIPath | string | `"/"` |  |
| ingress.hostAdmin | string | `"admin.iq-server.demo"` |  |
| ingress.hostAdminPath | string | `"/"` |  |
| ingress.tls | list | `[]` |  |
| resources | object | `{}` |  |
| nodeSelector | object | `{}` |  |
| tolerations | list | `[]` |  |
| affinity | object | `{}` |  |
| persistence.enabled | bool | `true` |  |
| persistence.accessMode | string | `"ReadWriteOnce"` |  |
| persistence.storageSize | string | `"1Gi"` |  |
| configYaml.sonatypeWork | string | `"/sonatype-work"` |  |
| configYaml.server.applicationConnectors[0].type | string | `"http"` |  |
| configYaml.server.applicationConnectors[0].port | int | `8070` |  |
| configYaml.server.adminConnectors[0].type | string | `"http"` |  |
| configYaml.server.adminConnectors[0].port | int | `8071` |  |
| configYaml.server.requestLog.appenders[0].type | string | `"file"` |  |
| configYaml.server.requestLog.appenders[0].currentLogFilename | string | `"/var/log/nexus-iq-server/request.log"` |  |
| configYaml.server.requestLog.appenders[0].logFormat | string | `"%clientHost %l %user [%date] \"%requestURL\" %statusCode %bytesSent %elapsedTime \"%header{User-Agent}\""` |  |
| configYaml.server.requestLog.appenders[0].archivedLogFilenamePattern | string | `"/var/log/nexus-iq-server/request-%d.log.gz"` |  |
| configYaml.server.requestLog.appenders[0].archivedFileCount | int | `50` |  |
| configYaml.createSampleData | bool | `true` |  |
| configYaml.logging.level | string | `"ERROR"` |  |
| configYaml.logging.loggers."com.sonatype.insight.scan" | string | `"INFO"` |  |
| configYaml.logging.loggers."eu.medsea.mimeutil.MimeUtil2" | string | `"INFO"` |  |
| configYaml.logging.loggers."org.apache.http" | string | `"INFO"` |  |
| configYaml.logging.loggers."org.apache.http.wire" | string | `"ERROR"` |  |
| configYaml.logging.loggers."org.eclipse.birt.report.engine.layout.pdf.font.FontConfigReader" | string | `"WARN"` |  |
| configYaml.logging.loggers."org.eclipse.jetty" | string | `"INFO"` |  |
| configYaml.logging.loggers."org.apache.shiro.web.filter.authc.BasicHttpAuthenticationFilter" | string | `"INFO"` |  |
| configYaml.logging.loggers."com.sonatype.insight.audit".appenders[0].type | string | `"console"` |  |
| configYaml.logging.loggers."com.sonatype.insight.audit".appenders[0].threshold | string | `"INFO"` |  |
| configYaml.logging.loggers."com.sonatype.insight.policy.violation".appenders[0].type | string | `"console"` |  |
| configYaml.logging.loggers."com.sonatype.insight.policy.violation".appenders[0].threshold | string | `"INFO"` |  |
| configYaml.logging.appenders[0].type | string | `"console"` |  |
| configYaml.logging.appenders[0].threshold | string | `"INFO"` |  |
| configYaml.logging.appenders[0].logFormat | string | `"%d{'yyyy-MM-dd HH:mm:ss,SSSZ'} %level [%thread] %X{username} %logger - %msg%n"` |  |
| configYaml.logging.appenders[1].type | string | `"file"` |  |
| configYaml.logging.appenders[1].threshold | string | `"ALL"` |  |
| configYaml.logging.appenders[1].logFormat | string | `"%d{'yyyy-MM-dd HH:mm:ss,SSSZ'} %level [%thread] %X{username} %logger - %msg%n"` |  |
| configYaml.logging.appenders[1].currentLogFilename | string | `"/var/log/nexus-iq-server/clm-server.log"` |  |
| configYaml.logging.appenders[1].archivedLogFilenamePattern | string | `"/var/log/nexus-iq-server/clm-server-%d.log.gz"` |  |
| configYaml.logging.appenders[1].archivedFileCount | int | `50` |  |

## Contributing

Please see the [contributing guide](./CONTRIBUTING.md) if you are interested in contributing.
