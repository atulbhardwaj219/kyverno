# Sample Policies

Sample policies are designed to be applied to your Kubernetes clusters with minimal changes. To apply these policies to your cluster, install Kyverno and import the policies as follows:

**Install Kyverno**

````sh
kubectl create -f https://github.com/nirmata/kyverno/raw/master/definitions/install.yaml
````
<small>[(installation docs)](../documentation/installation.md)</small>

**Apply Kyverno Policies**

To start applying policies to your cluster, first clone the repo:

````bash
git clone https://github.com/nirmata/kyverno.git
cd kyverno
````

Import best_practices from [here](best_pratices):

````bash
kubectl create -f samples/best_practices
````

Import addition policies from [here](more):

````bash
kubectl create -f samples/more/
````

The policies are mostly validation rules in `audit` mode i.e. your existing workloads will not be impacted, but will be audited for policy complaince.

## Best Practice Policies

These policies are highly recommended.

1. [Run as non-root user](RunAsNonRootUser.md)
2. [Disable privileged containers and disallow privilege escalation](DisablePrivilegedContainers.md)
3. [Disallow new capabilities](DisallowNewCapabilities.md)
4. [Require Read-only root filesystem](RequireReadOnlyFS.md)
5. [Disallow use of bind mounts (`hostPath` volumes)](DisallowHostFS.md)
6. [Disallow `hostNetwork` and `hostPort`](DisallowHostNetworkPort.md)
7. [Disallow `hostPID` and `hostIPC`](DisallowHostPIDIPC.md)
8. [Disallow unknown image registries](DisallowUnknownRegistries.md)
8. [Disallow latest image tag](DisallowLatestTag.md)
10. [Disallow use of default namespace](DisallowDefaultNamespace.md)
11. [Require namespace limits and quotas](RequireNSLimitsQuotas.md)
12. [Require pod resource requests and limits](RequirePodRequestsLimits.md)
13. [Require pod `livenessProbe` and `readinessProbe`](RequirePodProbes.md)
14. [Default deny all ingress traffic](DefaultDenyAllIngress.md)


## Additional Policies

The policies provide additional best practices and are worthy of close consideration. These policies may require workload specific changes. 

15. [Limit use of `NodePort` services](LimitNodePort.md)
16. [Limit automount of Service Account credentials](DisallowAutomountSACredentials.md)
17. [Configure Linux Capabilities](AssignLinuxCapabilities.md)
18. [Limit Kernel parameter access](ConfigureKernelParmeters.md)


