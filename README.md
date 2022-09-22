# Custom Supply Chains

## Prerequisites

## Set Up

* Install templates
<pre> 
cd templates
kubectl apply -f .
</pre>
* Install Supply Chains
<pre>
cd supplychains
kubectl apply -f .
</pre>
* create roles and role bindings
<pre>
cd configs
kubectl apply -f rbac.yaml -n <your-namespace>
</pre>


## Developers flow

### Basic Flow  
Source (flux) -> Build Image (kpack) -> Deploy APP (deployment, service, HTTPProxy)
<pre>
kubectl apply -f configs/workload-deployer.yaml -n <your-namespace>
</pre>

### Gitops Flow
Source (flux) -> Build Image (kpack) -> Deploy APP (deployment, service, HTTPProxy) -> Config Provider (configmap) -> Config Writer (flux, gitactions)
<pre>
kubectl apply -f configs/workload.yaml -n <your-namespace>
</pre>





