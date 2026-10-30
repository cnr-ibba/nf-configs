# nf-core/configs: IBBA wf-basecalling specific configuration

Extra specific configuration for wf-basecalling pipeline

## Usage

Currently, two distinct profiles are managed within the [`ibba.config`](../../../conf/ibba.config) file: the `core` profile used for our internal *core* HPC cluster and the `galileo` profile used for the [Galileo 100 cluster](https://docs.hpc.cineca.it/hpc/galileo.html) at Cineca.

To use, run the pipeline with one of `-profile ibba,core` or `-profile ibba,galileo` according to the infrastructure you are targeting.

This will download and launch the wf-basecalling specific [`ibba.config`](../../../conf/pipeline/wf-basecalling/ibba.config) which has been pre-configured with a setup suitable for the IBBA infrastructure.

Example: `nextflow run cnr-ibba/wf-basecalling -profile ibba,core`

## wf-basecalling specific configurations for IBBA

This is not an nf-core pipeline, so the nf-core specific parameters (`config_profile_url`, `config_profile_contact`, `config_profile_description`, `config_profile_name`, `custom_config_base`) are set to `null` and listed, together with other generic parameters (`aws_queue`, `aws_image_prefix`, ...), in `schema_ignore_params` to avoid pipeline schema validation errors.

### galileo profile

Processes with the `gpu` label are run on the `g100_usr_interactive` queue:

- resource limits: 48 CPUs, 384.GB memory, 8.h time
- `maxForks = 5` to limit the number of jobs submitted to the cluster
- cluster options: `--account=${SLURM_JOB_ACCOUNT} --qos=normal --gpus=1`
- tasks are retried only for exit statuses 130-145 and 104, otherwise the pipeline finishes

Process `dorado` uses a custom container (`docker.io-bunop-dorado-v1.4.0-cuda11.8.0.img`) from `$NXF_SINGULARITY_CACHEDIR`.
