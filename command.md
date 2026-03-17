## 🚀 Deployment Steps

```bash
# 1. Start Minikube
minikube start

# 2. Apply the multi-container pod manifest
kubectl apply -f manifests/multi-container-pod.yaml

# 3. Watch pod initialization
kubectl get pods -w

# 4. Check container logs
kubectl logs multi-container-pod -c mysql-server
kubectl logs multi-container-pod -c mysql-client -f

# 5. Access MySQL
kubectl exec -it multi-container-pod -c mysql-client -- mysql -h 127.0.0.1 -u root -p
# Password: admin1234


Commands cheat sheet
# Pod operations
kubectl get pods
kubectl describe pod <pod-name>
kubectl logs <pod-name> -c <container-name>

# Exec into containers
kubectl exec -it <pod-name> -c <container-name> -- /bin/bash

# Port forwarding
kubectl port-forward pod/<pod-name> 3306:3306

# Delete resources
kubectl delete pod <pod-name>
