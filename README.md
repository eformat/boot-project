# boot-project

Helm Chart to help create the OpenShift projects based on good practices and out of the box OpenShift features.

Use this Helm Chart with ArgoCD when practicing "Everything as Code" using GitOps.

## Label Taxonomy

Common project labels. Adjust to suit. For example

| Label --|    Value   |  Comment    |
| ------- |------------|-------------|
| appId   |  app1      |  Application Identifier |

## Role Bindings

Group Role Bindings

## Resource Quota

Best practices for CPU limits and requests on Kubernetes

-- https://home.robusta.dev/blog/stop-using-cpu-limits

Setting a hard resource quota at the Project scope ensures that all workloads within this namespace will need to set these limits and requests less than the hard quota to be scheduled.

1. Use CPU requests for everything (if you need help setting them, see KRR)
2. Make sure they are accurate
3. Do not use CPU limits.

Memory limits and requests

1. Always use memory limits
2. Always use memory requests
3. Always set your memory requests equal to your limits

Persistent volume claims and total storage request.

## Egress IP

So we can identify Egress traffic from applications in this namespace on an external firewall.

## Network Policy

Default policies (additive)

- deny-by-default
- allow-from-openshift-ingress
- allow-same-namespace

## Operator Group

If true, create namespaced operator group.
