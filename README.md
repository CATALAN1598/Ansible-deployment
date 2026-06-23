# ansible-deployment

## ESK-cluster-deployment

Automatic **elasticsearch** / **kibana** cluster deployment without license features 
All of Authority certificate, certificate, password are used on a lab plateform and are here to describe how to use it.

## K8S-cluster-deployment

Automatic **kubernetes** cluster deployment with 3 master nodes, 3 workers nodes and a ngnix loadbalancer.

I use:
    
    - **OS** (Operating System):                debian 12
    - **CRI** (Container Runtime Interface):    containerd
    - **CNI** (Container Network Interface):    calico

The  playbooks are divided like:

    - 00-pre-install-k8s.yml:           All prerequisites
    - 10-install-haproxy.yml:           HA proxy installation before cluster boostrap
    - 21-configure-cgroupdriver.yml:    Configuration of kubelet and containerd
    - 30-boostrap-fisrt-master.yml:     Create cluster and init fisrt master
    - 31-join-other-master.yml:         Add and join all of other masters
    - 32-join-all-workers.yml:          Add and join all workers
    - 99-delete-cluster.yml:            Reset all node and delete cluster
    
