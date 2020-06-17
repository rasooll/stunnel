# Stunnel client helm chart
A stunnel client for using proxy in your cluster.  
Current chart version: `0.0.1`  
Stunnel version: `5.56-r1`

### Helm values:
```yaml
replicaCount: 1

image:
  repository: rasooll/stunnel
  pullPolicy: IfNotPresent
  tag: ""

imagePullSecrets: []
nameOverride: ""
fullnameOverride: ""

podAnnotations: {}

service:
  type: ClusterIP

resources: {}
  # limits:
  #   cpu: 100m
  #   memory: 128Mi
  #   ephemeral-storage: 50Mi
  # requests:
  #   cpu: 100m
  #   memory: 128Mi
  #   ephemeral-storage: 10Mi

nodeSelector: {}

tolerations: []

affinity: {}

servers: []
  # - name: socks
  #   adr: socks.example.com
  #   port: 1080
  #   psk: "username:encrypted-password-with-htpasswd"
  # - name: squid
  #   adr: squid.example.com
  #   port: 3128
  #   psk: ""
```
* `servers` is a list of your stunnel server and minimum one server is required.
* if your server does not secure with psk, you must use a empty string for psk.