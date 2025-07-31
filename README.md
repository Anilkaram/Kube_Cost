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
# Application 
<img width="1920" height="1080" alt="Screenshot (294)" src="https://github.com/user-attachments/assets/6d25f6b8-8ada-4ee9-bc3e-de5481045670" />
# Resources in K8S 
<img width="1920" height="1080" alt="Screenshot (295)" src="https://github.com/user-attachments/assets/e0fded2b-d0b1-4a24-8f27-665497b8dda9" />
# KubeCost Monitor
<img width="1920" height="1080" alt="Screenshot (296)" src="https://github.com/user-attachments/assets/f71d5885-8841-4193-94ab-37c4c82fc58c" />
# KubeCost Overview
<img width="1920" height="1080" alt="Screenshot (293)" src="https://github.com/user-attachments/assets/4f130fe1-390f-48b4-80f2-cebd2179ab77" />

