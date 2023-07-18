kubectl apply -f namespace.yaml

helm install -f values.yaml snake-game ./chart-simple-deploy -n my-namespace-1

helm list -n my-namespace-1

kubectl get secret/snake-game-secret -n my-namespace-1 -o yaml

kubectl exec -ti -n my-namespace-1 snake-game-deployment-d988c7c9d-mn4cl -- sh

kubectl port-forward service/snake-game-service 30081:80 -n my-namespace-1

helm uninstall snake-game -n my-namespace-1

helm install -f values.yaml snake-game ./chart-simple-deploy -n my-namespace-1 --dry-run --debug

