# nf-core/configs: IBBA Configuration

All nf-core pipelines have been successfully configured for use on the IBBA infrastructure. At the moment we are maintaining two different profiles to run
pipelines on the *core* HPC cluster and on the
[Galileo 100 cluster](https://wiki.u-gov.it/confluence/display/SCAIUS/UG3.3%3A+GALILEO100+UserGuide)
at cineca.

## Calling pipelines on *core* HPC cluster

To use, run the pipeline with `-profile ibba,core`. This will download and launch the [`ibba.config`](../conf/ibba.config) which has been pre-configured with a setup suitable for the IBBA *core* infrastructure.

## Calling pipelines on Galileo 100 cluster

To use, run the pipeline with `-profile ibba,galileo`. This will download and launch the [`ibba.config`](../conf/ibba.config) which has been pre-configured with a setup suitable for the Cineca *Galileo 100* infrastructure.
