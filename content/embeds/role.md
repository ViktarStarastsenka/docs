```yaml
apiVersion: rbac.authorization.k8s.io/v1
kind: Role
metadata:
  labels:
    app: redis-enterprise
  name: redis-enterprise-operator
rules:
  - apiGroups:
      - rbac.authorization.k8s.io
      - ""
    resources:
      - roles
      - serviceaccounts
      - rolebindings
    verbs:
      - create
      - get
      - update
      - patch
      - delete
  - apiGroups:
      - app.redislabs.com
    resources:
      - redisenterpriseclusters
      - redisenterpriseclusters/status
      - redisenterpriseclusters/finalizers
      - redisenterprisedatabases
      - redisenterprisedatabases/status
      - redisenterprisedatabases/finalizers
      - redisenterpriseremoteclusters
      - redisenterpriseremoteclusters/status
      - redisenterpriseremoteclusters/finalizers
      - redisenterpriseactiveactivedatabases
      - redisenterpriseactiveactivedatabases/status
      - redisenterpriseactiveactivedatabases/finalizers
    verbs:
      - delete
      - get
      - list
      - patch
      - create
      - update
      - watch
  - apiGroups:
      - ""
    resources:
      - secrets
    verbs:
      - update
      - get
      - create
      - patch
      - delete
      - list
      - watch
  - apiGroups:
      - ""
    resources:
      - endpoints
    verbs:
      - get
      - list
      - watch
  - apiGroups:
      - ""
    resources:
      - events
    verbs:
      - create
      - patch
  - apiGroups:
      - apps
    resources:
      - deployments
      - statefulsets
      - replicasets
    verbs:
      - create
      - delete
      - get
      - patch
      - update
      - list
      - watch
  - apiGroups:
      - policy
    resources:
      - poddisruptionbudgets
    verbs:
      - create
      - delete
      - get
      - list
      - watch
  - apiGroups:
      - ""
    resources:
      - configmaps
    verbs:
      - create
      - delete
      - get
      - update
      - watch
      - list
  - apiGroups:
      - ""
    resources:
      - persistentvolumeclaims
    verbs:
      - create
      - delete
      - get
      - update
      - list
      - watch
  - apiGroups:
      - ""
    resources:
      - pods
    verbs:
      - get
      - list
      - update
      - patch
      - delete
      - watch
  - apiGroups:
      - ""
    resources:
      - services
    verbs:
      - get
      - list
      - update
      - patch
      - create
      - delete
      - watch
  - apiGroups:
      - policy
    resourceNames:
      - redis-enterprise-psp
    resources:
      - podsecuritypolicies
    verbs:
      - use
  - apiGroups:
      - networking.k8s.io
    resources:
      - ingresses
    verbs:
      - create
      - patch
      - delete
      - list
      - update
      - get
      - watch
  - apiGroups:
      - networking.istio.io
    resources:
      - gateways
      - virtualservices
    verbs:
      - get
      - list
      - update
      - patch
      - create
      - delete
      - watch
```
