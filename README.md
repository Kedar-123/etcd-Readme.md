# Etcd package

etcd is a distributed key-value store designed to securely store data across a cluster. etcd is widely used in production on account of its reliability, fault-tolerance and ease of use.

## Configuration Reference

You can configure the following:

### etcd parameters

|Parameter|Description|Type|Default|
|---------|-----------|----|-------|
|image.pullPolicy|etcd image pull policy|string|IfNotPresent|
|auth.rbac.rootPassword|Root user password. The root user is always root|string|""|

### etcd statefulset parameters

|Parameter|Description|Type|Default|
|---------|-----------|----|-------|
|replicaCount|	Number of etcd replicas to deploy|integer|1|
|podManagementPolicy|Pod management policy for the etcd statefulset|string|Parallel|
|containerPorts.client|Client port to expose at container level|integer|2379|
|containerPorts.peer|Peer port to expose at container level|integer|2380|
|podSecurityContext.fsGroup|Set etcd pod's Security Context fsGroup|integer|1001|
|containerSecurityContext.runAsUser|Set etcd container's Security Context runAsUser|integer|1001|
|containerSecurityContext.runAsNonRoot|Set etcd container's Security Context runAsNonRoot|string|TRUE|
|livenessProbe.initialDelaySeconds|Initial delay seconds for livenessProbe|integer|60|
|livenessProbe.periodSeconds|Period seconds for livenessProbe|integer|30|
|livenessProbe.timeoutSeconds|Timeout seconds for livenessProbe|integer|5|
|livenessProbe.failureThreshold|Failure threshold for livenessProbe|integer|5|
|livenessProbe.successThreshold|Success threshold for livenessProbe|integer|1|
|readinessProbe.initialDelaySeconds|Initial delay seconds for readinessProbe|integer|60|
|readinessProbe.periodSeconds|Period seconds for readinessProbe|integer|10|
|readinessProbe.timeoutSeconds|Timeout seconds for readinessProbe|integer|5|
|readinessProbe.failureThreshold|Failure threshold for readinessProbe|integer|5|
|readinessProbe.successThreshold|Success threshold for readinessProbe|integer|1|
|startupProbe.enabled|Enable startupProbe|string|FALSE|
|startupProbe.initialDelaySeconds|Initial delay seconds for startupProbe|integer|0|
|startupProbe.periodSeconds|Period seconds for startupProbe|integer|10|
|startupProbe.timeoutSeconds|Timeout seconds for startupProbe|integer|5|
|startupProbe.failureThreshold|Failure threshold for startupProbe|integer|60|
|startupProbe.successThreshold|Success threshold for startupProbe|integer|1|
|initContainers|Add additional init containers to the etcd pod|string|[]|

### Persistence parameters

|Parameter|Description|Type|Default|
|---------|-----------|----|-------|
|persistence.storageClass|Persistent Volume Storage Class|string|""|
|persistence.size|PVC Storage Request for etcd data volume|integer|8Gi|

### Network Policy parameters

|Parameter|Description|Type|Default|
|---------|-----------|----|-------|
|networkPolicy.enabled|Enable creation of NetworkPolicy resources|string|FALSE|
|networkPolicy.extraIngress|Add extra ingress rules to the NetworkPolicy|string|[]|
|networkPolicy.extraEgress|Add extra ingress rules to the NetworkPolicy|string|[]|

### Service account parameters

|Parameter|Description|Type|Default|
|---------|-----------|----|-------|
|serviceAccount.name|Name of the service account to create or use|string|""|














