```yaml
apiVersion: v1
kind: Service
metadata:
  name: admission
  labels:
    app: redis-enterprise
spec:
  ports:
    - port: 443
      protocol: TCP
      targetPort: 8443
  selector:
    name: redis-enterprise-operator
```
