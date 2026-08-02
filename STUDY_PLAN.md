# AZ-104 Mastery Plan

This plan is aligned to Microsoft's skills measured as of April 17, 2026. It is mastery-based: calendar estimates are adjustable, but the exit criteria are not.

## Learning loop

Each tightly scoped lesson follows the same loop:

1. **Retrieve:** answer two or three questions from memory.
2. **Learn:** study one concept and its decision rules from official sources.
3. **Predict:** state what Azure will do before touching the portal or CLI.
4. **Operate:** complete a small portal task, then inspect or repeat it with CLI/PowerShell where useful.
5. **Troubleshoot:** diagnose one deliberately broken or misleading scenario.
6. **Explain:** justify the answer and reject the closest distractor.
7. **Record:** capture demonstrated understanding and any remaining gap.

## Mastery scale

- **0 — Unknown:** cannot yet recognize the concept.
- **1 — Recognize:** can identify terms or follow instructions.
- **2 — Explain:** can explain behavior and compare alternatives.
- **3 — Apply:** can complete a representative task and solve a fresh scenario.
- **4 — Troubleshoot:** can diagnose interactions, inspect effective configuration, and justify remediation.

A domain is ready to leave when all current objectives are at least level 3, high-risk objectives reach level 4, and the learner scores at least 80% on a fresh domain check while explaining the reasoning.

## Phase 0 — Baseline and setup

**Goal:** turn prior exposure into an evidence-based starting profile.

- Take a short custom identity/governance diagnostic without notes.
- Check prerequisites: subscriptions/tenants, portal access, Cloud Shell or local Azure CLI, PowerShell, and Bicep tooling.
- Run a small mixed AZ-900/AZ-104 prerequisite check for networking, operating systems, servers, virtualization, Cloud Shell, and deployment templates.
- Create the objective tracker and mark each skill 0–4.

**Exit:** environment is usable and the first gap map exists.

## Phase 1 — Consolidate identities and governance (20–25%)

**Do not repeat the overview.** Focus on application and ambiguity:

- Entra roles versus Azure RBAC roles.
- Role definition versus role assignment; principal, role, scope; inheritance and effective access.
- Least privilege and narrowest workable scope.
- Policy definitions, initiatives, assignments, parameters, effects, compliance, exemptions, and remediation.
- RBAC versus Policy versus locks versus tags.
- Users, groups, guests, licenses, and SSPR prerequisites and scope.
- Subscription/resource-group/management-group boundaries and cost controls.

**Hands-on proof:** create test identities/groups where licensing permits; make and inspect scoped role assignments; inspect inherited access; assign a safe audit policy; apply tags and a lock; create or inspect a budget; then clean up lab resources.

**Exit:** at least 80% on fresh scenarios and a correct end-to-end explanation of effective access and governance interactions.

## Phase 2 — Implement and manage storage (15–20%)

- Storage account choices, endpoints, performance, redundancy, failover implications, encryption, and object replication.
- Authentication and authorization: Entra ID/RBAC, account keys, SAS, stored access policies, firewalls, service endpoints, and private endpoints.
- Blob containers, access tiers, lifecycle management, versioning, snapshots, and soft delete.
- Azure Files, identity-based access, snapshots, and soft delete.
- Storage Explorer and AzCopy.

**Hands-on proof:** deploy a storage account; restrict network access; upload/copy data; issue and revoke constrained access; configure protection and lifecycle features; explain what survives each failure or deletion scenario.

**Exit:** select access and redundancy designs from requirements without confusing management-plane and data-plane permissions.

## Phase 3 — Deploy and manage compute (20–25%)

- Read, modify, export, convert, and deploy ARM templates or Bicep.
- VM sizing, disks, host encryption, moves, availability sets, availability zones, and scale sets.
- Azure Container Registry, Container Instances, and Container Apps; sizing and scaling.
- App Service plans, apps, scale, TLS/certificates, custom DNS, backups, networking, and deployment slots.

**Hands-on proof:** deploy infrastructure declaratively; create a VM and inspect its dependencies; make an availability/scale decision; deploy one container; configure an App Service slot and swap scenario where budget and access permit.

**Exit:** choose among compute services and availability options from operational requirements, and safely modify a supplied template.

## Phase 4 — Implement and manage virtual networking (15–20%)

- Address spaces, subnets, public IPs, peering, gateway transit constraints, and user-defined routes.
- NSGs, application security groups, priorities, statefulness, and effective rules.
- Bastion, service endpoints, and private endpoints.
- Azure DNS, internal/public Load Balancer, health probes, and troubleshooting.
- Network Watcher and Connection Monitor.

**Hands-on proof:** build a multi-subnet VNet; predict and test flows; change an NSG or route; peer VNets; configure private access to a PaaS resource; troubleshoot a failed connection from effective routes/rules and diagnostic tools.

**Exit:** correctly trace packet flow and name resolution before proposing a fix.

## Phase 5 — Monitor, back up, and recover (10–15%)

- Azure Monitor metrics versus logs; diagnostic settings; Log Analytics and basic KQL.
- Alert rules, action groups, and alert processing rules.
- VM, storage, and network insights; Network Watcher and Connection Monitor.
- Recovery Services vault versus Backup vault; policies; backup/restore; reports and alerts.
- Site Recovery replication, test failover, failover, and recovery concepts.

**Hands-on proof:** send diagnostic data to a workspace; query it; create an actionable alert; configure a backup policy; perform or walk through restore and failover decisions.

**Exit:** choose the correct telemetry or recovery tool and derive a diagnosis from evidence rather than guessing.

## Phase 6 — Integration and exam readiness

- Solve cross-domain cases where identity, networking, storage, compute, and monitoring interact.
- Practice time-boxed case studies, build-list questions, and least-change/least-privilege questions.
- Use the free Microsoft Practice Assessment as a readiness signal; maintain an error log by misconception, not by question wording.
- Re-study weak objectives, then retest with fresh scenarios.
- Use the Microsoft exam sandbox and recheck the live study guide before booking.

**Ready-to-book gate:** two fresh mixed assessments at 80% or higher, no domain below 75%, reasoned review of every miss, completion of core hands-on labs, and comfort with the exam interface. These thresholds are study rules, not a guarantee of passing.

## Suggested default cadence

Until the learner supplies a target date and weekly availability:

- Three focused sessions per week, 60–90 minutes each.
- One short retrieval session per week, 20–30 minutes.
- Rough allocation: identity consolidation 1 unit; storage 2; compute 3; networking 3; monitoring/recovery 2; integration and practice 2.
- Revisit older domains every week through mixed questions instead of finishing a domain and forgetting it.

## Immediate next step

Work through the identity/governance consolidation pack in `lessons/index.html`: complete each theory page and its matching lab, then take a short closed-book domain diagnostic. Use the quiz and lab evidence to decide whether identity/governance is ready to close or needs one targeted remediation lesson.
