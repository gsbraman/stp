## Charts
### Test ClusterIP Service
```
nc -v swagger-service 9080 -i 2
nc -v swagger-service.test.svc.cluster.local 9080 -i 2
```