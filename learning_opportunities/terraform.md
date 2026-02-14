# Learning Opportunities: Terraform (Infrastructure as Code)

> Context: Listed as "Exposure to Terraform" in the Canva Senior MLE - Visual Suite job ad.
> Goal: Just understand what it is and how it works. Not tested in interviews — 12 minutes of video is enough.

---

## What It Is

Terraform is an Infrastructure as Code (IaC) tool by HashiCorp. It lets you define cloud infrastructure (K8s clusters, GPU nodes, databases, networking) in declarative `.tf` config files, then `terraform apply` makes it real. Same mental model as K8s YAML manifests, but for the infrastructure layer underneath.

| K8s (what you know) | Terraform (equivalent) |
|---|---|
| `kubectl apply -f deployment.yaml` | `terraform apply` |
| YAML manifests | `.tf` files (HCL syntax) |
| Manages pods, services, etc. | Manages cloud resources (VMs, clusters, networking) |
| K8s reconciles desired state | Terraform reconciles desired state |
| `kubectl diff` | `terraform plan` |

**Key difference:** K8s manages resources *inside* a cluster. Terraform manages the *infrastructure itself* (the cluster, the cloud account, the networking, the DNS).

---

## Your Existing Foundation

- K8s YAML config experience — same declarative "desired state" pattern
- Azure cloud infrastructure — you've used what Terraform provisions
- Docker / CI/CD — declarative configuration mindset
- This will click fast given your background

---

## Learning Plan (~12 minutes total, Priority: LOW)

1. [ ] Watch [Terraform in 100 Seconds (Fireship)](https://www.youtube.com/watch?v=tomUWcQ0P3k) — 2 min, just the concept
2. [ ] Watch [Terraform in 10 Minutes for Absolute Beginners](https://www.youtube.com/watch?v=7NR7soSwYKk) — 10 min, covers basics with examples
3. [ ] (Optional) Watch [Terraform Basics by HashiCorp](https://www.youtube.com/watch?v=_45W3Z8XWL4) — 21 min, full workflow: `init`, `plan`, `apply`, `destroy`

**Key vocabulary to know:** HCL (HashiCorp Configuration Language), `terraform init`, `terraform plan`, `terraform apply`, `terraform destroy`, state file, provider, resource, module.

---

## How to Talk About It in Interviews

> "I haven't used Terraform directly, but I've worked with K8s manifests, Docker configs, and CI/CD pipelines — the declarative infrastructure-as-code pattern is familiar. I've watched the HashiCorp intro and understand the workflow: define resources in HCL, plan to preview changes, apply to provision. I'd pick up Terraform quickly."

---

## Summary

| Topic | Priority | Time Investment | Type |
|---|---|---|---|
| Terraform basics | LOW | 12 min | Videos |

**Don't over-invest here.** The job ad says "exposure" and it won't be tested.
