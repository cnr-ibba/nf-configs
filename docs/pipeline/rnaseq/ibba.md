# nf-core/configs: IBBA rnaseq specific configuration

Extra specific configuration for rnaseq pipeline

## Usage

Currently, two distinct profiles are managed within the [`ibba.config`](../../../conf/ibba.config) file: the `core` profile used for our internal *core* HPC cluster and the `galileo` profile used for the [Galileo 100 cluster](https://docs.hpc.cineca.it/hpc/galileo.html) at Cineca.

To use, run the pipeline with one of `-profile ibba,core` or `-profile ibba,galileo` according to the infrastructure you are targeting.

This will download and launch the rnaseq specific [`ibba.config`](../../../conf/pipeline/rnaseq/ibba.config) which has been pre-configured with a setup suitable for the IBBA infrastructure.

Example: `nextflow run nf-core/rnaseq -profile ibba,core`

## rnaseq specific configurations for IBBA

### galileo profile

Within *galileo* environment, pipelines should be called in *OFFLINE* mode.
See [Running nextflow offline](https://bioinfo-guidelines.readthedocs.io/en/latest/nextflow/troubleshooting.html#running-nextflow-offline) for more information.

- process `DUPRADAR` is set to `8 * task.attempt` CPUs, `64.GB * task.attempt` memory, `24.h * task.attempt` time and `maxRetries = 6`. Local scratch (`$TMPDIR`) is enabled for this process.
