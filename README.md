Automium Service: kubernetes 
======================================

[![Build Status](https://travis-ci.org/automium/service-kubernetes.svg?branch=master)](https://travis-ci.org/automium/service-kubernetes)

this project is meant to be used by [automium provisioner](https://github.com/automium/provisioner)

## variables

### MASTER

if true configure the instance as a kubernetes master node

### NODE

if true configure the instance as a kubernetes worker node

### ETCD

if true configure the instance as a etcd node

### KUBE_CONF _optional_

[kubespray variables](https://github.com/kubernetes-sigs/kubespray/blob/master/docs/vars.md)

es. in docker compose:
```yaml
environment:
  KUBE_CONF: |-
    podsecuritypolicy_enabled: true
    kubelet_custom_flags:
      - "--event-qps=0"
```

### RANCHER_URL _optional_

rancher http url

### RANCHER_CLUSTER_TOKEN _optional_

rancher token

### AUTOMIUM_AUTOSCALER_KUBECONFIG _optional_

base64 automium kubeconfig

### HOST_FILEBEAT_CONF
```yaml
HOST_FILEBEAT_CONF: |-
  filebeat_conf:
    output.elasticsearch:
      hosts: ["http://myelasticseach.mydomain.tld:9200"]
  filebeat_enable_modules:
    - system
  filebeat_enabled: true
  filebeat_state: started
```


## usage

setup service var:
```
export SERVICE=automium/service-kubernetes
export MASTER=true
export NODE=true
export ETCD=true
export RANCHER_URL=http://rancher.local
export RANCHER_CLUSTER_TOKEN=237dh928gd2
export AUTOMIUM_AUTOSCALER_KUBECONFIG=YPBpVmVyq2lvbjogdjEKY2x1c3...RlWTFVMjU2Vkc1Q2RYTjZVMGhpYm1wUfo=
```

and follow the guide [here](https://github.com/automium/provisioner/blob/master/README.md#guide)
