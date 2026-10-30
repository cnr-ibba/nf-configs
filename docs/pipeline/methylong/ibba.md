# nf-core/configs: IBBA methylong specific configuration

Extra specific configuration for methylong pipeline

## Usage

Currently, two distinct profiles are managed within the [`ibba.config`](../../../conf/ibba.config) file: the `core` profile used for our internal *core* HPC cluster and the `galileo` profile used for the [Galileo 100 cluster](https://docs.hpc.cineca.it/hpc/galileo.html) at Cineca.

To use, run the pipeline with one of `-profile ibba,core` or `-profile ibba,galileo` according to the infrastructure you are targeting.

This will download and launch the methylong specific [`ibba.config`](../../../conf/pipeline/methylong/ibba.config) which has been pre-configured with a setup suitable for the IBBA infrastructure.

Example: `nextflow run nf-core/methylong -profile ibba,core`

## methylong specific configurations for IBBA

### galileo profile

Within *galileo* environment, pipelines should be called in *OFFLINE* mode.
See [Running nextflow offline](https://bioinfo-guidelines.readthedocs.io/en/latest/nextflow/troubleshooting.html#running-nextflow-offline) for more information.

- process `PORECHOP_PORECHOP` memory is increased to `72.GB * task.attempt`, since some datasets need more memory than the default.
