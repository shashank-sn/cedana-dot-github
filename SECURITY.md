# Security policy

## Report a vulnerability

Report a security issue to contact@cedana.ai. Please keep it out of public issues, pull requests and discussions.

You can also send it privately on GitHub: open the repository's **Security** tab and click **Report a vulnerability**. Only Cedana's maintainers can see a report sent that way. If a repository has no **Report a vulnerability** button, use the [Security tab of cedana/cedana](https://github.com/cedana/cedana/security).

Please include:

- the component and version: for example the daemon release, a plugin, the Helm chart version or an image tag
- what an attacker could do, and what access they need first
- steps to reproduce, or a proof of concept
- your environment: Linux distribution and kernel, container runtime, Kubernetes or Slurm version, GPU and driver

## What happens next

- We acknowledge your report and keep you updated, by email or in the private advisory on GitHub.
- We confirm the problem, assess how severe it is and tell you our plan.
- We fix it, publish a release and a GitHub security advisory, and credit you unless you ask us not to.
- Please give us time to release a fix before you disclose details publicly.

## Scope

In scope: the code in Cedana's public repositories, the release binaries, the Helm chart and the images under hub.docker.com/u/cedana.

## What Cedana needs on a host

Cedana checkpoints and restores running processes, so it runs with high privileges by design:

- The daemon requires root.
- On Kubernetes, the helper DaemonSet runs with privilege escalation and installs the daemon and its dependencies on the host, and the controller can list, checkpoint and restore all pods.
- The optional shared-memory setting changes the host file system and mount points.

These are expected behavior, not vulnerabilities. Details: [Cedana installation: what changes on your cluster](https://cedana.com/blog/cedana-installation-cluster-changes/)
