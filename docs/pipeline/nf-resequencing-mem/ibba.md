# nf-core/configs: IBBA nf-resequencing-mem specific configuration

Extra specific configuration for nf-resequencing-mem pipeline

## Usage

Currently, two distinct profiles are managed within the [`ibba.config`](../../../conf/ibba.config) file: the `core` profile used for our internal *core* HPC cluster and the `galileo` profile used for the [Galileo 100 cluster](https://wiki.u-gov.it/confluence/display/SCAIUS/GALILEO100+User+Guide) at Cineca.

To use, run the pipeline with one of `-profile ibba,core` or `-profile ibba,galileo` according to the infrastructure you are targeting.

This will download and launch the nf-resequencing-mem specific [`ibba.config`](../../../conf/pipeline/nf-resequencing-mem/ibba.config) which has been pre-configured with a setup suitable for the IBBA infrastructure or for the available infrastructure at *cineca*.

Example: `nextflow run cnr-ibba/nf-resequencing-mem -profile ibba,core`

## nf-resequencing-mem specific configurations for IBBA

### galileo profile

Within *galileo* environment, pipelines should be called in *OFFLINE* mode.
See [Running nextflow offline](https://bioinfo-guidelines.readthedocs.io/en/latest/nextflow/troubleshooting.html#running-nextflow-offline) for more information.

- process `PICARD_MARKDUPLICATES` is set with `ext.args = "--TMP_DIR \$TMPDIR"`
- process `SNPEFF_DOWNLOAD` is called on `g100_all_serial` queue
