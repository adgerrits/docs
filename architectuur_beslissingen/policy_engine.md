# Policy engine

## Status

Review.

## Context

A Cloud Broker wants to enforce custom policies in a (multi tenant) Kubernetes cluster, for example:

- To avoid tenants hijacking Ingress Controllers from other tenants
- To enforce tenants deploying images from a platform registry

Custom policies complement [default policies](https://kubernetes.io/docs/concepts/policy/) such as limit ranges, resource quotas and pod security policies, and are managed by a policy agent.

The [CNF Landscape](https://landscape.cncf.io) defines two open source policy agents in the category Provisioning - Security & Compliance:

- [Open Policy Agent](https://www.openpolicyagent.org) (status Graduated at time of writing)
- [Kyverno](https://kyverno.io) (status Sandbox at time of writing)

## Decision

CNO starts with supporting Kyverno, because:

- Kyverno is lightweight (no separate programming language needed)
- Kyverno is Kubernetes native (custom resource definitions)
- Kyverno is capable of validating AND mutating
- Kyverno has HA on its roadmap

Advantages and disadvantages, ref. [analysis](https://neonmirrors.net/post/2021-02/kubernetes-policy-comparison-opa-gatekeeper-vs-kyverno/):

### Advantages OPA

- Capable of expressing very complex policies
- More establishment in the community
- Supports multiple replicas for availability and scale

### Disadvantages OPA

- Requiring a programming language is a serious learning curve which generates large amounts of technical debt and increases time to value
- Mutation ability is in nascent stage; no generation ability means its usefulness is limited to predominantly validation use cases
- Policy is complex, often lengthy, and requires multiple documents to implement

### Advantages Kyverno

- Dramatic simplicity of policy expression allowing Kubernetes-style composition
- Solid mutation abilities
- Generation and syncing ability is unique and allows new use cases; quick time to value and high degree of flexibility

### Disadvantages Kyverno

- Highly complex policy generally not possible since no programming language exposed
- Young, still largely unproven due to lower establishment
- API lookup ability is in nascent stage
- Not HA yet (roadmap)

## Consequences

Cloud brokers can deploy custom policies in a multi tenant Kubernetes cluster.

Cloud consumers cannot (yet) deploy custom policies, as they would be able to disrupt the (namespace scoped) policies that are deployed by the cloud broker.
