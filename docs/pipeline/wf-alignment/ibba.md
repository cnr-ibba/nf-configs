# nf-core/configs: IBBA wf-alignment specific configuration

Extra specific configuration for wf-alignment pipeline

## Usage

Currently, two distinct profiles are managed within the [`ibba.config`](../../../conf/ibba.config) file: the `core` profile used for our internal *core* HPC cluster and the `galileo` profile used for the [Galileo 100 cluster](https://docs.hpc.cineca.it/hpc/galileo.html) at Cineca.

To use, run the pipeline with one of `-profile ibba,core` or `-profile ibba,galileo` according to the infrastructure you are targeting.

This will download and launch the wf-alignment specific [`ibba.config`](../../../conf/pipeline/wf-alignment/ibba.config) which has been pre-configured with a setup suitable for the IBBA infrastructure.

Example: `nextflow run cnr-ibba/wf-alignment -profile ibba,core`

## wf-alignment specific configurations for IBBA

This is not an nf-core pipeline, so the nf-core specific parameters (`config_profile_url`, `config_profile_contact`, `config_profile_description`, `config_profile_name`, `custom_config_base`) are set to `null` and listed, together with other nf-core generic parameters, in `schema_ignore_params` to avoid pipeline schema validation errors.
