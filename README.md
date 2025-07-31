# Kube_Cost
Kubernetes Cost management

Step 1: Install Kubecost
Running the following command will also install Prometheus and Grafana in the namespace supplied. View install configuration options here.
helm install kubecost cost-analyzer \
--repo https://kubecost.github.io/cost-analyzer/ \
--namespace kubecost --create-namespace

Step 2: Enable port-forward
kubectl port-forward --namespace kubecost deployment/kubecost-cost-analyzer 9090

Step 3: See the data!
You can now view the deployed frontend by visiting the following link. Publish :9090 as a secure endpoint on your cluster to remove the need to port forward. http://localhost:9090

Updating Kubecost
After installing Kubecost, you will be able to update your version with the following command:

helm repo add kubecost https://kubecost.github.io/cost-analyzer/ && \
helm repo update && \
helm upgrade kubecost kubecost/cost-analyzer -n kubecost

Deleting Kubecost
To uninstall Kubecost and its dependencies, run the following command:

helm uninstall kubecost -n kubecost
