# Etcd package

etcd is a distributed key-value store designed to securely store data across a cluster. etcd is widely used in production on account of its reliability, fault-tolerance and ease of use.

## Configuration Reference

You can configure the following:

### etcd parameters

|Parameter|Description|Type|Default|
|---------|-----------|----|-------|
|image.pullPolicy|etcd image pull policy|string|IfNotPresent|
|auth.rbac.rootPassword|Root user password. The root user is always root|string|""|
|podManagementPolicy|Pod management policy for the etcd statefulset|string|Parallel|
|containerPorts.client|Client port to expose at container level|integer|2379|
|containerPorts.peer|Peer port to expose at container level|integer|2380|
|podSecurityContext.fsGroup|Set etcd pod's Security Context fsGroup|integer|1001|
|containerSecurityContext.runAsUser|Set etcd container's Security Context runAsUser|integer1001|
|containerSecurityContext.runAsNonRoot|Set etcd container's Security Context runAsNonRoot|string|TRUE|
|livenessProbe.initialDelaySeconds|Initial delay seconds for livenessProbe|integer|60|
|livenessProbe.periodSeconds|Period seconds for livenessProbe|integer|30|
|livenessProbe.timeoutSeconds|Timeout seconds for livenessProbe|ineger|5|
|livenessProbe.failureThreshold|Failure threshold for livenessProbe|ineger|5|
|livenessProbe.successThreshold|Success threshold for livenessProbe|ineger|1|
|readinessProbe.initialDelaySeconds|Initial delay seconds for readinessProbe|ineger|60|
|readinessProbe.periodSeconds|Period seconds for readinessProbe|ineger|10|
|readinessProbe.timeoutSeconds|Timeout seconds for readinessProbe|ineger|5|
|readinessProbe.failureThreshold|Failure threshold for readinessProbe|ineger|5|
|readinessProbe.successThreshold|Success threshold for readinessProbe|ineger|1|
|startupProbe.enabled|Enable startupProbe|string|FALSE|
|startupProbe.initialDelaySeconds|Initial delay seconds for startupProbe|ineger|0|
|startupProbe.periodSeconds|Period seconds for startupProbe|ineger|10|
|startupProbe.timeoutSeconds|Timeout seconds for startupProbe|ineger|5|
|startupProbe.failureThreshold|Failure threshold for startupProbe|ineger|60|
|startupProbe.successThreshold|Success threshold for startupProbe|ineger|1|
|initContainers|Add additional init containers to the etcd pod|string|[]|
