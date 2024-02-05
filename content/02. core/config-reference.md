---
title: Config Reference
description: ''
position: 16
category: 'Policy Reporter'
---

# Config Reference

Configuration file reference with all possible options.

```yaml
kubeconfig: '~/.kube/config' 

api:
  port: 8080
  logging: false
  basicAuth:
    username: ""
    password: ""
    secretRef: ""

rest:
  enabled: false

database:
  type: "sqlite"
  database: ""
  username: ""
  password: ""
  host: ""
  enableSSL: false
  dsn: ""
  secretRef: ""
  mountedSecret: ""

dbfile: "sqlite-database.db"

metrics:
  enabled: false
  mode: detailed # available modes are detailed (default), simple and custom
  customLabels: ["namespace", "rule", "policy", "report", "kind", "name", "status", "severity", "category", "source"] # available only in custom mode
  filter:
    sources:
      exclude: []
      include: []
    status:
      exclude: []
      include: []
    severities:
      exclude: []
      include: []
    namespaces:
      exclude: []
      include: []
    policies:
      exclude: []
      include: []

priorityMap: {}

reportFilter:
  namespaces:
    include: []
    exclude: []
  clusterReports:
    disabled: false

redis:
  enabled: false
  address: "redis:6379"
  database: 1
  prefix: "policy-reporter"
  username: ""
  password: ""

loki:
  host: ""
  path: ""
  # HTTP BasicAuth
  username: ""
  password: ""
  minimumPriority: "warning"
  skipExistingOnStartup: true
  customLabels: {}
  sources: []
  filter:
    namespaces:
      include: []
      exclude: []
    policies:
      include: []
      exclude: []
    priorities:
      include: []
      exclude: []
    channels: []

elasticsearch:
  host: ""
  index: "policy-reporter"
  rotation: "daily"
  minimumPriority: ""
  skipExistingOnStartup: true
  typelessApi: false
  sources: []
  filter:
    namespaces:
      include: []
      exclude: []
    policies:
      include: []
      exclude: []
    priorities:
      include: []
      exclude: []
    channels: []

slack:
  webhook: ""
  minimumPriority: ""
  skipExistingOnStartup: true
  sources: []
  filter:
    namespaces:
      include: []
      exclude: []
    policies:
      include: []
      exclude: []
    priorities:
      include: []
      exclude: []
    channels: []

discord:
  webhook: ""
  minimumPriority: ""
  skipExistingOnStartup: true
  sources: []
  filter:
    namespaces:
      include: []
      exclude: []
    policies:
      include: []
      exclude: []
    priorities:
      include: []
      exclude: []
    channels: []

teams:
  webhook: ""
  minimumPriority: ""
  skipExistingOnStartup: true
  sources: []
  filter:
    namespaces:
      include: []
      exclude: []
    policies:
      include: []
      exclude: []
    priorities:
      include: []
      exclude: []
    channels: []

ui:
  host: ""
  minimumPriority: "warning"
  skipExistingOnStartup: true
  sources: []

webhook:
  host: ""
  headers: {}
  minimumPriority: ""
  skipExistingOnStartup: true
  sources: []
  filter:
    namespaces:
      include: []
      exclude: []
    policies:
      include: []
      exclude: []
    priorities:
      include: []
      exclude: []
    channels: []

s3:
  endpoint: ""
  region: ""
  bucket: ""
  prefix: "policy-reporter"
  secretAccessKey: ""
  accessKeyID: ""
  minimumPriority: "warning"
  skipExistingOnStartup: true
  sources: []
  filter:
    namespaces:
      include: []
      exclude: []
    policies:
      include: []
      exclude: []
    priorities:
      include: []
      exclude: []
    channels: []

kinesis:
  endpoint: ""
  region: ""
  streamName: ""
  secretAccessKey: ""
  accessKeyID: ""
  minimumPriority: "warning"
  skipExistingOnStartup: true
  sources: []
  filter:
    namespaces:
      include: []
      exclude: []
    policies:
      include: []
      exclude: []
    priorities:
      include: []
      exclude: []
    channels: []

securityHub:
  endpoint: ""
  region: ""
  accountID: ""
  secretAccessKey: ""
  accessKeyID: ""
  minimumPriority: "warning"
  skipExistingOnStartup: true
  sources: []
  filter:
    namespaces:
      include: []
      exclude: []
    policies:
      include: []
      exclude: []
    priorities:
      include: []
      exclude: []
    channels: []

gcs:
  credentials: ""
  bucket: ""
  minimumPriority: "warning"
  skipExistingOnStartup: true
  sources: []
  filter:
    namespaces:
      include: []
      exclude: []
    policies:
      include: []
      exclude: []
    priorities:
      include: []
      exclude: []
    channels: []

  googleChat:
    webhook: ""
    minimumPriority: ""
    skipExistingOnStartup: true
    mountedSecret: ""
    secretRef: ""
    sources: []
    filter:
      namespaces:
        include: []
        exclude: []
      policies:
        include: []
        exclude: []
      priorities:
        include: []
        exclude: []
      channels: []

  telegram:
    token: ""
    chatID: ""
    host: "" # optional proxy host
    minimumPriority: ""
    skipExistingOnStartup: true
    mountedSecret: ""
    secretRef: ""
    sources: []
    filter:
      namespaces:
        include: []
        exclude: []
      policies:
        include: []
        exclude: []
      priorities:
        include: []
        exclude: []
      channels: []

emailReports:
  clusterName: ""
  smtp:
    host: ""
    port: 465
    username: ""
    password: ""
    from: ""
    encryption: ""

  summary:
    to: []
    filter:
      disableClusterReports: false
      namespaces:
        include: []
        exclude: []
      sources:
        include: []
        exclude: []
    channels: []
  violations:
    to: []
    filter:
      disableClusterReports: false
      namespaces:
        include: []
        exclude: []
      sources:
        include: []
        exclude: []
    channels: []

leaderElection:
  enabled: false
  releaseOnCancel: true
  leaseDuration: 15
  renewDeadline: 10
  retryPeriod: 2
```
