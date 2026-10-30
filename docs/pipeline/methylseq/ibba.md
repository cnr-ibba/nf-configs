# nf-core/configs: IBBA methylseq specific configuration

Extra specific configuration for methylseq pipeline

## Usage

Currently, two distinct profiles are managed within the [`ibba.config`](../../../conf/ibba.config) file: the `core` profile used for our internal *core* HPC cluster and the `galileo` profile used for the [Galileo 100 cluster](https://docs.hpc.cineca.it/hpc/galileo.html) at Cineca.

To use, run the pipeline with one of `-profile ibba,core` or `-profile ibba,galileo` according to the infrastructure you are targeting.

This will download and launch the methylseq specific [`ibba.config`](../../../conf/pipeline/methylseq/ibba.config) which has been pre-configured with a setup suitable for the IBBA infrastructure.

Example: `nextflow run nf-core/methylseq -profile ibba,core`

## methylseq specific configurations for IBBA

Resources for process `BISMARK_ALIGN` are tuned following the Bismark multicore formula: `min(cpus/3, memory/13GB)` for normal libraries and `min(cpus/5, memory/18GB)` for non-directional libraries.

### core profile

- process `BISMARK_ALIGN` is set to `6 * task.attempt` CPUs and `26.GB * task.attempt` memory, which gives 2 Bismark cores (normal) or 1 core (non-directional).

### galileo profile

- process `BISMARK_ALIGN` is set to `24 * task.attempt` CPUs, `104.GB * task.attempt` memory and `1.d * task.attempt` time, which gives 8 Bismark cores (normal) or 4 cores (non-directional).
