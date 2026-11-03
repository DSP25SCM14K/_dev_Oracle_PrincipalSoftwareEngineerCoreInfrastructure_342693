# Role and company research — requisition 342693

**Prepared November 3, 2026** · Portfolio: Dev Kumar · Resume: `_dev_Oracle_PrincipalSoftwareEngineerCoreInfrastructure_342693.docx`

## Posting snapshot

The Oracle Careers posting identifies **Principal Software Engineer, Core Infrastructure**, job 342693, in **Nashville, Tennessee**. It was posted October 16, 2026, is a regular employee / individual contributor role, and states a 6–10+ year experience range. The posting is unusually explicit about the operational lifecycle as well as design: build and begin architecting elastic distributed components; set and meet scalability requirements; optimize high-throughput code/data paths and large-scale retrieval/storage/processing; design capacity tests; survive maintenance and failure through redundancy, replication, failover, and partition-aware policies; protect SLOs with overload controls; define telemetry/KPIs; validate correctness with fault injection and brownouts; troubleshoot incidents and mentor; secure multi-tenant infrastructure; and automate infrastructure updates, patches, and rollbacks.

**Source:** [Oracle Careers — job 342693](https://careers.oracle.com/en/sites/jobsearch/job/342693/) (accessed November 3, 2026).

## What the job is asking for

This is a senior individual-contributor role with architecture ownership that is expected to grow. The strongest evidence is not a list of tools: it is a coherent record that connects design choices to system behavior and measured outcomes. The posting clusters into six engineering problems:

1. **Scale and data plane.** Define measurable scalability requirements, use distributed state, scale elastically, and optimize the parts of the data path that dominate latency and throughput. Retrieval, storage, processing, and representative load tests are all explicitly named.
2. **Reliability under real faults.** Redundancy and failover are not enough by themselves; replication and synchronization must preserve correctness. Network partitions require an intentional consistency/availability choice, and overload needs load shedding, throttling, and rate limiting.
3. **SLOs and observability.** KPIs, telemetry, dashboards, and alerts should expose performance and reliability gaps early enough for operators to act.
4. **Correctness evidence.** Fault injection and brownout scenarios should test behavior under partial failure, while replication/synchronization tests establish integrity and durability.
5. **Operations and security.** Production troubleshooting, operational readiness, on-call and mentoring are part of the work. Multi-tenant encryption/access controls, remediation, and maintained compliance records are also called out.
6. **Safe change.** Infrastructure as code, automation, and explicit change plans should make patching, updating, and rollback routine and verifiable, including designs that need no customer maintenance window.

## Company context: Oracle and OCI

Oracle describes its mission around helping people use data to discover insights, and its portfolio spans cloud infrastructure, databases, applications, and AI. Oracle's FY2026 results announcement reported strong growth in both cloud infrastructure and cloud applications, with infrastructure revenue growth described as a key driver. That makes dependable infrastructure capacity and service operation strategically central—not merely an internal platform concern. See [Oracle company information](https://www.oracle.com/corporate/), [Oracle Cloud Infrastructure](https://www.oracle.com/cloud/), and [Oracle's FY2026 results announcement](https://www.oracle.com/news/announcement/q4fy26-earnings-release-2026-06-10/).

OCI's documented architecture organizes resources into regions, availability domains, and fault domains. Regions are independent geographic areas; availability domains are isolated data-center groupings; fault domains separate hardware within an availability domain. Oracle's guidance explains that deployment placement, replication, redundancy, and failover design determine whether those layers actually improve application resilience. OCI's high-availability guidance also treats monitoring and failover readiness as design elements, and explains how dependent component SLAs combine into an end-to-end service objective. These details make the posting's focus on resiliency, observability, replication, and partition behavior especially concrete. See [OCI Regions and Fault Domains](https://docs.oracle.com/en/cloud/foundation/cloud_architecture/governance/regions.html), [OCI Resiliency](https://docs.oracle.com/en-us/iaas/Content/cloud-adoption-framework/era-resiliency.htm), and [OCI High Availability](https://docs.oracle.com/en-us/iaas/Content/cloud-adoption-framework/high-availability.htm).

Oracle's cloud product page describes elastic compute, bare metal, GPUs/HPC, block/file/object/archive storage, managed Kubernetes, and global cloud data-center infrastructure. The breadth reinforces that a core infrastructure engineer must reason about interfaces and failure behavior across multiple service layers, not only one application. This is an inference from the product scope and the posting's explicit cross-cutting responsibilities. See [Oracle Cloud Infrastructure](https://www.oracle.com/cloud/).

## Resume evidence mapped to the posting

| Posting theme | Evidence in Dev Kumar's resume |
|---|---|
| Elasticity, performance, scalability | Sprouts AI: sub-200 ms p95 at 5× peak traffic through Kubernetes/OCI scaling and autoscaling. Resilience Inc: 3× data-path throughput. Tata Steel: 40% faster API responses; 50M+ sensor events/day at sub-second latency. |
| Availability, partitions, maintenance-free operations | Sprouts AI: 99.99% availability, zero maintenance windows, cross-zone replication, failover and rolling upgrades; overload controls and partition tradeoffs. |
| Replication, state, durability | Resilience Inc: zero-loss regional failover using quorum replication/synchronization with etcd/Raft. Tata Steel: five-plant durability and availability using replication and failover. |
| Correctness testing | Resilience Inc: 20+ defects found with fault injection and brownouts. The Keystone project adds test evidence from 41 injected faults, as described in the resume. |
| Telemetry and operational response | Sprouts AI: 45% MTTR reduction using KPIs, OpenTelemetry, Grafana, alerts, incident response and RCA. Tata Steel: undetected failures down 50%, repeat incidents down 35%. |
| Safe patching and change | Resilience Inc: rollout time down 60%, zero high-impact regressions through Terraform, CI/CD, staged releases and rollback. Tata Steel: Ansible patch/rollback and change management. |
| Tenant security and compliance | Sprouts AI: encryption in transit/at rest, IAM, isolation, remediation and compliance documentation; no cross-tenant security incidents. Tata Steel: RBAC/TLS and closure of all critical audit findings. |
| Mentoring and operational readiness | Mentored engineers at Sprouts AI, Resilience Inc, and Tata Steel; Resilience Inc includes mentoring four engineers. |

The resume states 8+ years of experience, consistent with the posting's 6–10+ year range. The clearest portfolio through-line is measured infrastructure behavior under load and fault: elastic capacity, replicated state, safe degradation, tested recovery, and actionable operating signals. This is a synthesis of the posting and resume—not a claim about Oracle's unpublished team plans.

## Useful interview proof points to prepare

For each result, be ready to explain the baseline, measurement window, workload shape, and what you personally owned. In particular:

- Define p95 versus p99 and describe how the 5× load was generated, including saturation and tail-latency behavior.
- Walk through a partition/failover decision: which operations prioritize availability, which require stronger consistency, and how replicas catch up.
- Explain how zero-loss failover was measured and what acknowledgment/quorum boundary made the claim valid.
- Give one fault-injection or brownout scenario, the invariant under test, and how the defect was detected.
- Show how the 45% MTTR change was calculated, and connect telemetry to a specific response/runbook improvement.
- Detail a staged infrastructure update, health gate, abort condition, and rollback path.
- Separate security controls you designed from controls inherited from the platform, and explain how tenant isolation was verified.

## Sources

- [Oracle Careers — Principal Software Engineer, Core Infrastructure (342693)](https://careers.oracle.com/en/sites/jobsearch/job/342693/)
- [Oracle company information](https://www.oracle.com/corporate/)
- [Oracle Cloud Infrastructure](https://www.oracle.com/cloud/)
- [Oracle FY2026 results announcement, June 10, 2026](https://www.oracle.com/news/announcement/q4fy26-earnings-release-2026-06-10/)
- [OCI Regions and Fault Domains](https://docs.oracle.com/en/cloud/foundation/cloud_architecture/governance/regions.html)
- [OCI Resiliency](https://docs.oracle.com/en-us/iaas/Content/cloud-adoption-framework/era-resiliency.htm)
- [OCI High Availability](https://docs.oracle.com/en-us/iaas/Content/cloud-adoption-framework/high-availability.htm)
- [OCI Service Level Agreements](https://docs.oracle.com/en-us/iaas/Content/General/Reference/slastatement.htm)
