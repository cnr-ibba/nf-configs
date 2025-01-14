# nf-core/configs: IBBA fecthngs specific configuration

Extra specific configuration for nf-resequencing-mem pipeline

## Usage

To use, run the pipeline with `-profile ibba`.

This will download and launch the nf-resequencing-mem specific [`ibba.config`](../../../conf/pipeline/nf-resequencing-mem/ibba.config) which has been pre-configured with a setup suitable for the IBBA infrastructure.

Example: `nextflow run cnr-ibba/nf-resequencing-mem -profile ibba`

## nf-resequencing-mem specific configurations for IBBA

Resources has been lowered to reduce the number of CPUs and the amount of memory.
Only a few process well be launched at a time to avoid overloading of network.
