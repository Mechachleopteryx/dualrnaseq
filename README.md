# ![nf-core/dualrnaseq](docs/images/nf-core-dualrnaseq_logo.png)

**Dual RNA-seq pipeline**.

[![GitHub Actions CI Status](https://github.com/nf-core/dualrnaseq/workflows/nf-core%20CI/badge.svg)](https://github.com/nf-core/dualrnaseq/actions)
[![GitHub Actions Linting Status](https://github.com/nf-core/dualrnaseq/workflows/nf-core%20linting/badge.svg)](https://github.com/nf-core/dualrnaseq/actions)
[![Nextflow](https://img.shields.io/badge/nextflow-%E2%89%A520.04.0-brightgreen.svg)](https://www.nextflow.io/)

[![install with bioconda](https://img.shields.io/badge/install%20with-bioconda-brightgreen.svg)](https://bioconda.github.io/)
[![Docker](https://img.shields.io/docker/automated/nfcore/dualrnaseq.svg)](https://hub.docker.com/r/nfcore/dualrnaseq)
[![Get help on Slack](http://img.shields.io/badge/slack-nf--core%20%23dualrnaseq-4A154B?logo=slack)](https://nfcore.slack.com/channels/dualrnaseq)

## Introduction

The pipeline is built using [Nextflow](https://www.nextflow.io), a workflow tool to run tasks across multiple compute infrastructures in a very portable manner. It comes with docker containers making installation trivial and results highly reproducible.

## Quick Start

1. Install [`nextflow`](https://nf-co.re/usage/installation)

2. Install any of [`Docker`](https://docs.docker.com/engine/installation/), [`Singularity`](https://www.sylabs.io/guides/3.0/user-guide/) or [`Podman`](https://podman.io/) for full pipeline reproducibility _(please only use [`Conda`](https://conda.io/miniconda.html) as a last resort; see [docs](https://nf-co.re/usage/configuration#basic-configuration-profiles))_

3. Download the pipeline and test it on a minimal dataset with a single command:

    ```bash
    nextflow run nf-core/dualrnaseq -profile test,<docker/singularity/podman/conda/institute>
    ```

    > Please check [nf-core/configs](https://github.com/nf-core/configs#documentation) to see if a custom config file to run nf-core pipelines already exists for your Institute. If so, you can simply use `-profile <institute>` in your command. This will enable either `docker` or `singularity` and set the appropriate execution settings for your local compute environment.

4. Start running your own analysis!

    <!-- TODO nf-core: Update the example "typical command" below used to run the pipeline -->

    ```bash
    nextflow run nf-core/dualrnaseq -profile <docker/singularity/podman/conda/institute> --input '*_R{1,2}.fastq.gz' --genome GRCh37
    ```

See [usage docs](https://nf-co.re/dualrnaseq/usage) for all of the available options when running the pipeline.

## Documentation

The nf-core/dualrnaseq pipeline comes with documentation about the pipeline: [usage](https://nf-co.re/dualrnaseq/usage) and [output](https://nf-co.re/dualrnaseq/output).

<!-- TODO nf-core: Add a brief overview of what the pipeline does and how it works -->

## Credits

nf-core/dualrnaseq was originally written by Bozena Mika-Gospodorz, Regan Hayward.
[![Nextflow](https://img.shields.io/badge/nextflow-%E2%89%A519.10.0-brightgreen.svg)](https://www.nextflow.io/)
[![nf-core](https://img.shields.io/badge/nf--core-pipeline-brightgreen.svg)](https://nf-co.re/)

[![GitHub Actions CI Status](https://github.com/nf-core/dualrnaseq/workflows/nf-core%20CI/badge.svg)](https://github.com/nf-core/dualrnaseq/actions)
[![GitHub Actions Linting Status](https://github.com/nf-core/dualrnaseq/workflows/nf-core%20linting/badge.svg)](https://github.com/nf-core/dualrnaseq/actions)

[![Docker Container available](https://img.shields.io/docker/automated/nfcore/dualrnaseq.svg)](https://hub.docker.com/r/dualrnaseq/dualrnaseq/)
[![Install with Singularity](https://img.shields.io/badge/use%20with-singularity-purple.svg)](https://www.sylabs.io/docs/)
[![install with bioconda](https://img.shields.io/badge/install%20with-bioconda-brightgreen.svg)](http://bioconda.github.io/)

## Dual RNA-seq pipeline

### Description

**nf-core/dualrnaseq** is an analysis pipeline for the analysis of Dual RNA-seq data. Dual RNA-seq is an experimental method for interrogating host-pathogen interactions through simultaneous RNA-seq.

The workflow merges host and pathogen genome annotations taking into account differences in annotation conventions, then processes raw data from
 FastQ inputs ([FastQC](https://www.bioinformatics.babraham.ac.uk/projects/fastqc/),
 [BBDuk](https://jgi.doe.gov/data-and-tools/bbtools/bb-tools-user-guide/bbduk-guide/)),
  quantifies gene expression
   ([STAR](https://github.com/alexdobin/STAR) and
    [HTSeq](https://htseq.readthedocs.io/en/master/); [STAR](https://github.com/alexdobin/STAR), [Salmon](https://combine-lab.github.io/salmon/) and [tximport](https://bioconductor.org/packages/release/bioc/html/tximport.html); or [Salmon](https://combine-lab.github.io/salmon/) in quasimapping mode and [tximport](https://bioconductor.org/packages/release/bioc/html/tximport.html)),
     and performs quality-control on the results
          ([MultiQC](http://multiqc.info/)), as well as generating a number of custom summary plots and separate results tables for the pathogen and host. See the [output documentation](docs/output.md) for more details of the results.

### Nextflow

The pipeline is built using [Nextflow](https://www.nextflow.io), a workflow tool to run tasks across multiple compute infrastructures in a very portable manner. It comes with Docker containers making installation trivial and results highly reproducible.

## Documentation

The nf-core/dualrnaseq pipeline comes with documentation about the pipeline, found in the `docs/` directory:

1. [Introduction](docs/introduction.md)
2. [Installation](https://nf-co.re/usage/installation)
3. Pipeline configuration
    * [Local installation](https://nf-co.re/usage/local_installation)
    * [Adding your own system config](https://nf-co.re/usage/adding_own_config)
    * [Reference genomes](https://nf-co.re/usage/reference_genomes)
    * [Parameters](docs/parameters.md)
4. [Running the pipeline](docs/usage.md)
5. [Output and how to interpret the results](docs/output.md)
6. [Troubleshooting](https://nf-co.re/usage/troubleshooting)

## Credits

nf-core/dualrnaseq was originally written by Bozena Mika-Gospodorz with support from Regan Hayward.

## Contributions and Support

If you would like to contribute to this pipeline, please see the [contributing guidelines](.github/CONTRIBUTING.md).

For further information or help, don't hesitate to get in touch on the [Slack `#dualrnaseq` channel](https://nfcore.slack.com/channels/dualrnaseq) (you can join with [this invite](https://nf-co.re/join/slack)).

## Citation

You can cite the `nf-core` publication as follows:

> **The nf-core framework for community-curated bioinformatics pipelines.**
>
> Philip Ewels, Alexander Peltzer, Sven Fillinger, Harshil Patel, Johannes Alneberg, Andreas Wilm, Maxime Ulysse Garcia, Paolo Di Tommaso & Sven Nahnsen.
>
> _Nat Biotechnol._ 2020 Feb 13. doi: [10.1038/s41587-020-0439-x](https://dx.doi.org/10.1038/s41587-020-0439-x).
> ReadCube: [Full Access Link](https://rdcu.be/b1GjZ)
