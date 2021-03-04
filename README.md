# kind-demo

## Run one control plane and one worker node
Use cluster01-kind.yaml in create-cluster.sh and run ./create-cluster.sh

## Run three control planes and three worker nodes with HAProxy load balancer in front of worker nodes
Use cluster01-multi.yaml in create-cluster.sh and run ./create-cluster.sh

## Delete the cluster
Run `kind delete cluster --name cluster01`

## List all nodes
Run `kubectl get nodes`

## List all pods
Run `kubectl get po --all-namespaces`

## Check nginx-ingress-controller pod
Run `kubectl get po -n ingress-nginx`

## List all containers
Run `docker ps`

## Deploy a custom HAProxy container for worker load balancing
./HAProxy-ingress.sh

## Inspect HAProxy load balancer logs
Run `docker logs HAProxy-workers-lb`

## Delete the HAProxy container
Run `docker rm HAProxy-works-lb --force`

## Simulate a kuberlet failure
Run `docker exec cluster01-worker systemctl stop kubelet`
`kubectl het nodes`

## Reschedule nginx-ingress-controller to simulate HAProxy HA
Run `kubectl delete po <pod_id> -n ingress-nginx`
