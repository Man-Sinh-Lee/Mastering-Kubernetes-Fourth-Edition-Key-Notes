Kubernetes API server manage cluster-wide policies, ensure resource validity, and enforce security protocols
- CRUD: create, update, delete k8s resources
- validate and process API requests, ensure meet the desired state
- authenticating users: maps creds to identities: client certificates, passwords, bearer tokens, and JWT tokens (for service accounts),  OpenID Connect, webhooks, Keystone, authenticating proxy,LDAP(webhook token)
- Impersonation: users, groups and extra name
- Authorizing requests: --authorization-mode={AlwaysDeny,AlwaysAllow, ABAC,RBAC,Node,Webhook}
- Using admission control plugins: controller modifies requests, runs validating or mutating mode.Plugins: NamespaceLifecycle,LimitRanger,ServiceAccount,Persisten
tVolumeLabel,DefaultStorageClass,MutatingAdmissionWebhook,ValidatingAdmissi-onWebhook,ResourceQuota,DefaultTolerationSeconds