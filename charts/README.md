## Charts
### Install Charts
```
helm repo add stp https://gsbraman.github.io/stp/
helm search repo stp/swagger --versions
helm install swagger stp/swagger --set namespace=test --version 7.0.10
helm upgrade swagger stp/swagger --set namespace=test --version 7.0.11
helm history swagger --namespace test
helm rollback swagger 1 --namespace test
```
### Test ClusterIP Service
```
nc -v swagger-service 9080 -i 2
nc -v swagger-service.test.svc.cluster.local 9080 -i 2
```
### Test route
```
curl -k https://swagger-test.apps-crc.testing/swagger
curl -kI https://swagger-test.apps-crc.testing/swagger
curl -kI -s -w "%{http_code}" https://swagger-test.apps-crc.testing/swagger

curl -kI http://swagger-test.apps-crc.testing/swagger
curl -kI -w "%{http_code}" http://swagger-test.apps-crc.testing/swagger
```