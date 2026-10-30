# nf-core/configs: IBBA nf-treeseq specific configuration

Extra specific configuration for nf-treeseq pipeline

## Usage

Currently, two distinct profiles are managed within the [`ibba.config`](../../../conf/ibba.config) file: the `core` profile used for our internal *core* HPC cluster and the `galileo` profile used for the [Galileo 100 cluster](https://docs.hpc.cineca.it/hpc/galileo.html) at Cineca.

To use, run the pipeline with one of `-profile ibba,core` or `-profile ibba,galileo` according to the infrastructure you are targeting.

This will download and launch the nf-treeseq specific [`ibba.config`](../../../conf/pipeline/nf-treeseq/ibba.config) which has been pre-configured with a setup suitable for the IBBA infrastructure.

Example: `nextflow run cnr-ibba/nf-treeseq -profile ibba,core`

## nf-treeseq specific configurations for IBBA

No pipeline-specific tuning is required: the file only sets the `config_profile_contact` and `config_profile_description` parameters.
