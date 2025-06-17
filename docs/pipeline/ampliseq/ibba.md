# nf-core/configs: ibba ampliseq specific configuration

Extra specific configuration for the ampliseq pipeline.

## Usage

Currently, two distinct profiles are managed within the [`ibba.config`](../../../conf/ibba.config) file: the `core` profile used for our internal *core* HPC cluster and the `galileo` profile used for the [Galileo 100 cluster](https://docs.hpc.cineca.it/hpc/galileo.html) at Cineca.

To use, run the pipeline with one of `-profile ibba,core` or `-profile ibba,galileo` according to the infrastructure you are targeting.

This will download and launch the ampliseq specific [`ibba.config`](../../../conf/pipeline/ampliseq/ibba.config)
which has been pre-configured with a setup suitable for the IBBA infrastructure or for the available infrastructure at *cineca*.

Example: `nextflow run nf-core/ampliseq -profile ibba,core`

## ampliseq specific configurations for ibba

Specific configurations for IBBA has been made for ampliseq.

### core profile

Lower memory requirements for processes `process_low`, `process_medium`, `process_high`
and `process_high_memory` are set to 6, 12, 40 and 64 GB respectively.

### galileo profile

Within *galileo* environment, pipelines should be called in *OFFLINE* mode.
See [Running nextflow offline](https://bioinfo-guidelines.readthedocs.io/en/latest/nextflow/troubleshooting.html#running-nextflow-offline) for more information.
