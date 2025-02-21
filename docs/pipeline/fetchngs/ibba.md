# nf-core/configs: IBBA fecthngs specific configuration

Extra specific configuration for fetchngs pipeline

## Usage

Currently, two distinct profiles are managed within the [`ibba.config`](../../../conf/ibba.config) file: the `core` profile used for our internal *core* HPC cluster and the `galileo` profile used for the [Galileo 100 cluster](https://wiki.u-gov.it/confluence/display/SCAIUS/GALILEO100+User+Guide) at Cineca.

To use, run the pipeline with one of `-profile ibba,core` or `-profile ibba,galileo` according to the infrastructure you are targeting.

This will download and launch the fetchngs specific [`ibba.config`](../../../conf/pipeline/fetchngs/ibba.config) which has been pre-configured with a setup suitable for the IBBA infrastructure.

Example: `nextflow run nf-core/fetchngs -profile ibba,core`

## fetchngs specific configurations for IBBA

### core profile

Resources has been lowered to reduce the number of CPUs and the amount of memory.
Only a few process well be launched at a time to avoid overloading of network.
