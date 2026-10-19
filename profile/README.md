![Cedana](https://github.com/user-attachments/assets/2cfe56a2-d292-4e62-a5bf-39cb2ab03c37)

Cedana is automated GPU checkpointing and migration infrastructure that increases the useful work your GPUs deliver. By preserving full workload state (CUDA context, KV cache) transparently across multi-GPU and multi-node jobs, Cedana increases effective GPU utilization, makes cold starts faster and predictable, and resumes workloads automatically on failure with no work lost.

### What Cedana fixes

- **Work lost to interruptions.** A failed GPU, a spot reclaim, a node drain, a Slurm time limit or an out-of-memory kill no longer sends a job back to the start. It resumes as of its last checkpoint.
- **Slow starts.** A model server restores from a checkpoint instead of loading its weights and building its engine again.
- **Jobs stuck where they started.** A running job can move to another node, so maintenance and rebalancing do not have to wait for jobs to finish.

The single-GPU and multi-GPU-on-a-single-node tiers ship in production today. Multi-node, where a single workload spans hundreds or thousands of GPUs across many nodes, is in design partnership with leading enterprises and neoclouds.

### Who uses Cedana

Cedana works with inference platforms, supercomputing centers, government and academic labs, pharma R&D, quant funds, and neoclouds, including Caltech.

### Where to start

- [cedana](https://github.com/cedana/cedana): the open-source daemon and CLI that checkpoint and restore processes and containers, built on CRIU
- [cedana-helm-charts](https://github.com/cedana/cedana-helm-charts): install Cedana on Kubernetes
- [cedana-samples](https://github.com/cedana/cedana-samples): CPU and GPU workloads to try it on
- [Docs](https://docs.cedana.ai): Kubernetes, Slurm and daemon guides, and the API reference
- [Benchmarks](https://cedana.com/benchmarks/): measured cold starts and restores, with the method

From the Cedana blog:

- [How Cedana checkpoint and restore works](https://cedana.com/blog/how-cedana-checkpoint-restore-works/)
- [What Cedana saves in a checkpoint, and its limits](https://cedana.com/blog/what-cedana-saves/)
- [Cedana installation: what changes on your cluster](https://cedana.com/blog/cedana-installation-cluster-changes/)
- [Cedana multi-node checkpointing: what ships today](https://cedana.com/blog/cedana-multi-node-checkpointing/)

Questions about the platform or a design partnership: [talk to Cedana](https://cedana.com/demo/). Bugs: open an issue in the repo concerned.
